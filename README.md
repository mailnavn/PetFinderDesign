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
### Bank transfer
- payment service uses either bank account transaction using payment gateway
- For bank transfer, the account number is stored encrypted
- User constent taken for storing account number
- account number deleted after 1 day (via scheuler)
- transfered via payment gateway (checkout.com)
- API Token/Key obtained for payment
- API does transcation and records it

### Secure paypal transfer
- Paypal's payout is chosen
- Senders paypal email account is used 
- paypal payment gateway api will facilitate transfer via payout service
- Account number not taken
- If receiver has paypal account ,receiver will get money via paypal
- If receiver does not have paypal account ,there are instructions on email on how to receive money from paypal

In either case, the transcations are recorded in Pet finder database


## Storage
- Dynamo db chosen for storage
- scalability and performance reason
- Cost effective
- less relational data
