- log in IAM management console
- create role for common use cases -- EC2
<img width="1726" alt="image" src="https://user-images.githubusercontent.com/81428296/177415375-b5bad285-da3f-4e16-aea9-f97ccb7036d6.png">
<img width="1612" alt="image" src="https://user-images.githubusercontent.com/81428296/177415438-c24c0495-593c-4693-b1ce-57087dc29638.png">

- choose the S3 read-only police
<img width="1737" alt="image" src="https://user-images.githubusercontent.com/81428296/177415661-23b6f353-3a42-4904-bced-62c18a7b8249.png">
<img width="1665" alt="image" src="https://user-images.githubusercontent.com/81428296/177415755-1f64ff82-5937-4445-bcb7-0fec03f164a3.png">

- attach the profile to the targeted instance in EC2
<img width="1564" alt="image" src="https://user-images.githubusercontent.com/81428296/177416304-b196ebc0-9ca8-4a86-b679-0ebb1be451cb.png">
<img width="837" alt="image" src="https://user-images.githubusercontent.com/81428296/177416421-2ec765cc-2b82-4618-8382-4c137aea1cb0.png">

- valid the permission on s3 side
  * login the S3 and select the bucket you wanna verify the policy for
<img width="1067" alt="image" src="https://user-images.githubusercontent.com/81428296/177416737-7c505b76-09e6-4954-a871-b4179c48660f.png">

  * got to permission module, and go to bucket policy part
<img width="1033" alt="image" src="https://user-images.githubusercontent.com/81428296/177417077-63103fa3-d5ef-405f-b465-77dd42d6d9e0.png">

 
