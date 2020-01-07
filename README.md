# Serverless Notes App API

__[Scratch](https://ligerx-serverless-notes-app.netlify.com/) is a note taking app built with full-stack serverless technology.__

This repo is for the serverless backend API. The front end React app repo is located [here](https://github.com/Ligerx/serverless-stack-client).

#### Tech Stack

![Serverless Diagram](./serverless-diagram.png)

_Diagram taken from the [AWS site](https://aws.amazon.com/getting-started/projects/build-serverless-web-app-lambda-apigateway-s3-dynamodb-cognito/)_

##### AWS Services
- __Lambda & API Gateway__ for the serverless API
- __DynamoDB__ for the database
- __Cognito__ for user authentication and securing the APIs
- __S3__ for file uploads

##### Other Tech
- __React.js__ for the single page app
- __Stripe__ for processing credit card payments
- __Seed__ for automating Serverless deployments
- __Netlify__ for automating React deployments

---

#### Usage

To use this repo locally you need to have the [Serverless framework](https://serverless.com) installed.

``` bash
$ npm install serverless -g
```

Clone this repo and install the NPM packages.

``` bash
$ git clone https://github.com/Ligerx/serverless-stack-api.git
$ npm install
```

Run a single API on local.

``` bash
$ serverless invoke local --function list --path event.json
```

Where, `event.json` contains the request event info and looks something like this.

``` json
{
  "requestContext": {
    "authorizer": {
      "claims": {
        "sub": "USER-SUB-1234"
      }
    }
  }
}
```

Finally, run this to deploy to your AWS account.

``` bash
$ serverless deploy
```

This project refers to an `.env` file for secret environment variables that are not checking in to the repo.

---

This project was built following the [Serverless Stack guide](https://serverless-stack.com/).
