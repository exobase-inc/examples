# Exobase API Example/Template

This is a runnable template for an Exobase API.

## Modules
There is one module (`health`) which has one function (`ping`). To add more endpoints add more module directories with more function files. Every file should export one default composed endpoint that starts with a root hook and ends with the endpoint function. For example, the `ping` endpoint exports a default composed function that starts with a root hook (`useLambda`) and ends with the endpoint function `pingEndpoint`.

## Deploy
You can deploy this function into AWS Lambda with Exobase in a few steps.

1. Create an AWS Account
2. Createa an Exobase Account
3. Create an IAM user in AWS called `exobase`
4. Under the AWS cloud provider configuration in Exobase set the secret id and key for the created user you just made in AWS. This gives Exobase permission to build infrastructure in you're AWS account on your behalf.
5. Have a drink, the hard part is done :cheers:
6. In Exobase, create a new service in any platform you have. In the service creation wizard choose API, AWS, Lambda, Typescript.
7. Copy the GitHub url of this repository into the text box for public GitHub repo
8. Select the `master` branch
9. Exobase will take you back to the platform services page when the service is made. It is not deployed yet. Just click Deploy and wait...
10. When the deploy has succeeded, you'll see a url in the service details. You can send a request to `{api url}/health/ping` to trigger the ping endpoint and get the pong response.

## Run Locally
Install dependencies with `yarn` then start the API with `yarn dev`.