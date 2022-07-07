#### the main issue is to update pip3:

### Below is an example of deploying paramoki dependency to lambda layer in Python 3.8
1. log in the ubuntu instance
2. install python 3.8
3. make 3.80 default
<img width="760" alt="image" src="https://user-images.githubusercontent.com/81428296/177836677-760cb708-3248-47c0-8da9-fedfb55e00f9.png">
4. install pip
<img width="755" alt="image" src="https://user-images.githubusercontent.com/81428296/177836839-4892d685-60e6-48c8-b85c-9b799640187c.png">
5. create a directory
<img width="616" alt="image" src="https://user-images.githubusercontent.com/81428296/177836948-000f4a35-3f70-418a-a11a-039f1ce34385.png">
6. install the paramoki package, here it may crash due to many reasons
<img width="747" alt="image" src="https://user-images.githubusercontent.com/81428296/177837043-81c08f2c-47d1-4a0e-8ecd-bfcbc5c8d43d.png">
  6.1 i install python3.8-dev first. it fixed part of issue, but there are still issues
  <img width="700" alt="image" src="https://user-images.githubusercontent.com/81428296/177837127-67030870-6aa8-4b98-acbb-07441dfb8870.png">
  6.2 then i install libffi-dev, but there are still issues
  <img width="420" alt="image" src="https://user-images.githubusercontent.com/81428296/177837284-06e87282-b67c-4cd8-841f-9a3d78abd940.png">
  6.3 i even tried this one, but there is still issues
  <img width="553" alt="image" src="https://user-images.githubusercontent.com/81428296/177837487-6f4a2686-4b3f-438a-8505-9096c8d1b635.png">
  6.4 finally i trid this and it works, just cannot use --system at the end anymore
  <img width="751" alt="image" src="https://user-images.githubusercontent.com/81428296/177837602-6e35df24-db0a-4b33-95e2-aaa60a6d43de.png">
  <img width="769" alt="image" src="https://user-images.githubusercontent.com/81428296/177837737-f54db14c-4907-42a2-b495-2c6709eb518b.png">
  <img width="747" alt="image" src="https://user-images.githubusercontent.com/81428296/177837823-7c537d57-1f46-4499-9130-cc09b9550c75.png">
7. install zip and zip the folder
  <img width="415" alt="image" src="https://user-images.githubusercontent.com/81428296/177837923-69bdd883-0c72-4cb1-b799-3ff1384628e5.png">
  first para is the package name, the second para -- '.' means the current directory
  <img width="478" alt="image" src="https://user-images.githubusercontent.com/81428296/177837968-cd81a924-bdfe-442a-8e17-800cef95d334.png">

8. then install aws comand line interface to ubuntu:
  <img width="845" alt="image" src="https://user-images.githubusercontent.com/81428296/177836124-8acc8f73-f072-4db0-95f3-94d33c364b12.png">
  Then copy file to S3
  <img width="735" alt="image" src="https://user-images.githubusercontent.com/81428296/177838212-56edb84b-ba72-47f4-ac01-b17061ff5cc9.png">

