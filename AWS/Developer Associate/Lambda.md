## AWS Lambda Function Configuration
### Lambda 설정에서 바꿀 수 있는 거
- 언어
- 핸들러
- 메모리랑 CPU allocation 변경
- 128 MB에서 3008MB까지 (64MB Increments)- Lambda max execution is 900 seconds (in 1 second increments)
- 권한
     - IAM Roles grant function permissio ns
- 환경변수
    - key:value 페어로
    - KMS를 이용해서 encryption 적용 (at rest)
- 네트워크 VPC
    - 서브넷
    - Security Group
- DLQ (Dead Letter Queue) : let us see what data made function crash!
- Concurrency - specify maximum # of concurrent invocations of your function (max is 1000 concurrent functions)
- Tags 

## AWS Lambda Function Packages
### "aka deployment packages" are zip packages of all the code and dependencies required by your Lambda function when it runs
- Can upload zipfile!
- Function packages include:
  - Your handler file
  - Custom libraries or packages
  - Any other application code that integrates with your handler
  - Third-party packages from providers like npm or pip that your function requires
- Specific examples
  - node.js - including node_modules folder with the npm dependencies


## Lambda Versions and Aliases
- Support versioning
- different versions have unique ARNs, so you can manage them for differnet environments like Productio, Staging or  Development

- Aliases are also supported
  - like a pointer to a specific Lambda version
  - can invoke a function using aliases without having to know which version of t he function is being referenced
  - Aliases have static ARN but can point to any version of the same function
  - Can also be used to split traffic between Lambda verions

- Benefits of versions and aliases
  - Easier workflow and management of stages
  - Avoid having to reconfigure event sources

## Lambda API actions
- several API actions when using CLI 
- look for API actions not in the video too!

