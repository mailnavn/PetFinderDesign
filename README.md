# PetFinderDesign

The Petfinder consits of 3 main components
1. UI Web APP 
2. Pet finder service (core backend)
3. Payment service (for reward)

## UI Web App
- Containerized Web API 
- Hosted on the Fargate 
- Connected to ELB for load balancing
- Connected to cognito for authentication
- UI App communicates with Pet finder service by using a pet finder client app that will pass the token obtained from client id and secret. 
- The UI app will then be able call the end-points exposed at the api gateway


## Pet Finder Service
- Backend servcie for pet finding
- Mostly serverless, event driven system
- API Gateway connected to cognito
- API gateway has end points for various actions like add, update, query, finding pets


## Payment Service


## Storage
- Dynamo db chosen for storage
- scalability and performance reason
- Cost effective
- less relational data
