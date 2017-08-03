# serverless-typescript-project-template

A template for a serverless aws project with typescript.

## Install

Of course you can just clone the repository:


   ```bash
   git clone git@github.com:bastian-meier/serverless-typescript-project-template.git
   ``` 
   
But you could also use the [serverless-typescript-generator](https://github.com/bastian-meier/serverless-typescript-generator).


## Important files and Folders:

* src/lambda

   This Folder holds yout lambda functions created with *npm run create*
   
* src/shared

   Folder for shared resources for your lambda functions
   
## Scripts

* npm run create

    creates a new lambda function

* npm run lint

    lints all your lambda functions and your shared resources
    
* npm run deploy

    deploys all your lambda function to aws, this function needs your aws keys, read **adding aws keys to serverless** for Informations
    If you just want to to deploy a single Function, call *npm run deploy* inside the lambda Function Folder
  
## usable links

* [serverless docs](https://serverless.com/framework/docs/providers/aws/)
* [typescript docs](https://www.typescriptlang.org/docs/home.html)
* [aws lambda docs](http://docs.aws.amazon.com/lambda/latest/dg/welcome.html)
    
## adding aws keys to serverless

1. Create or login to your Amazon Web Services Account and go to the Identity & Access Management (IAM) page.

2. Click on **Users** and then **Add user**. Enter a name in the first field to remind you this User is the Framework, like `serverless-admin`. Enable **Programmatic access** by clicking the checkbox. Click **Next** to go through to the Permissions page. Click on **Attach existing policies directly**. Search for and select **AdministratorAccess** then click **Next: Review**. Check everything looks good and click **Create user**. Later, you can create different IAM Users for different apps and different stages of those apps.  That is, if you don't use separate AWS accounts for stages/apps, which is most common.

3. View and copy the **API Key** & **Secret** to a temporary place. You'll need it in the next step.
   
4. Run the **serverless config credentials** command:

   ```bash
   serverless config credentials --provider aws --key YOUR_KEY --secret YOUR_SECRET
   ``` 