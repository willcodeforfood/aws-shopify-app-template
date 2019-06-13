# aws-shopify-app-template
This is an example shopify embedded app framework built using serverless, aws lambda, api gateway, cognito react, and redux

## Getting started

1. Clone the repo
2. `nvm install 10 && nvm use 10`
3. `npm install serverless-webpack --save-dev`
4. Create your app in Shopify Partners Panel. It will ask for some URLs. Just fill in something -- we will fix this later.
5. In the root of your cloned repo, create `.env` and fill in the API keys you just got from Shopify. Skip the other configs for now. \*
6. `sls deploy` your app to AWS
7. After successful deployment, you will see some URLs listed under `endpoints:`. In the Shopify partners panel, under App Setup, add these URLs to the whitelist.
8. One of the URLs ends with `/app`. Put this one in the "App URL" field in Shopify.
9. You'll notice that all these URLs start with the same hostname, `/dev`. This should go in the `BASE_URL` field in `config.json`. Example: `https://wp73f55y9t.execute-api.us-east-1.amazonaws.com/dev`
10. Set up a Cognito UserPool and IdentityPool. Connect the UserPool to the IdentityPool, grab the PoolID and fill it in in the config (ToDo: Update code to pull this from config).


\* Example `.env` file:
```
SHOPIFY_API_KEY=this comes from Shopify.
SHOPIFY_API_SECRET=this comes from Shopify.
BASE_URL=This comes from serverless
SCOPES=This isn't used ... yet
```
