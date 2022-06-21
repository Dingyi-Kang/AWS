<img width="400" alt="image" src="https://user-images.githubusercontent.com/81428296/174861130-a1094f1f-30d4-430b-a076-600aefac5b42.png">

      #set($inputRoot = $input.path('$'))
      {
        "type" : "$inputRoot.type",
        "fileName":"$inputRoot.fileName",
        "timestamp":"$inputRoot.timestamp",
        "values": $input.json('$.values'),
        "userId": "$context.authorizer.claims.sub"
      }
      
      
### lambda functions
 
        const AWS = require('aws-sdk');
        const dynamodb = new AWS.DynamoDB({ region: 'us-east-2', apiVersion: '2012-08-10' });

        exports.handler = (event, context, callback) => {

            let array = event.values;

            console.log(array);

            const newValues = [];

            for (var i = 0; i < array.length; i++) {
                if (isNaN(array[i])) {
                    newValues.push({ S: array[i].toString() });
                }
                else {
                    newValues.push({ N: array[i].toString() });
                }

            }

            console.log(newValues);

            const params = {
                Item: {
                    "userId": {
                        S: event.userId
                    },
                    "type": {
                        S: event.type
                    },
                    "timestamp": {
                        S: event.timestamp
                    },
                    "fileName": {
                        S: event.fileName
                    },
                    "values": {
                        L: newValues
                    }
                },
                TableName: "HealthMetricsData"
            };

             const paramsToDirectory = {
                Item: {
                    "userId": {
                        S: event.userId
                    },
                    "type": {
                        S: event.type
                    },
                    "timestamp": {
                        S: event.timestamp
                    },
                    "fileName": {
                        S: event.fileName
                    }
                },
                TableName: "HealthMetricsDirectory"
            };


            dynamodb.putItem(params, function(err, data) {
                if (err) {
                    console.log(err);
                    callback(err);
                }
                else {
                    console.log(data);
                    //if succeed store data, store the fileName in directoryTable as well
                    dynamodb.putItem(paramsToDirectory, function(err, data) {
                        if (err) {
                            console.log(err);
                            callback(err);
                        }
                        else {
                            console.log(data);
                            callback(null, data);
                        }
                    });
                }
            });
        };
