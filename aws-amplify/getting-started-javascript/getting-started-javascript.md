https://docs.amplify.aws/start/q/integration/js/


# Steps
```sh
npm install -g @aws-amplify/cli
amplify configure
# user name:  amplify-user
npm i
amplify init
amplify add api
amplify push
amplify status
amplify add hosting
amplify publish
amplify console
amplify delete
amplify status
# Delete the user amplify-user
```



- **Amplify CLI :** Configure all the services needed to power your backend through a simple command line interface.
- **Amplify Libraries :** Use case-centric client libraries to integrate your app code with a backend using declarative interfaces.
- **Amplify UI Components :** UI libraries for React, React Native, Angular, Ionic, Vue and Flutter.
- **Amplify Hosting :** Amplify Hosting is an AWS service that provides a git-based workflow for continuous deployment & hosting of fullstack web apps. Cloud resources created by the Amplify CLI are also visible in the Amplify Console.

# Ojective
You will create a “Todo app” with a GraphQL API and to store and retrieve items in a cloud database, as well as receive updates over a realtime subscription.

- [Tutorial](https://docs.amplify.aws/start/getting-started/installation/q/integration/js/)

# Prerequisites && installation: 

## Prerequisites
- [Node.js](https://nodejs.org/en/) v14.x or later
```sh
node --version
```

- [npm](https://www.npmjs.com/) v6.14.4 or later
```sh
npm --version
```

- [git](https://git-scm.com/) v2.14.1 or later
```sh
git --version
```

## Create user (Only new)
https://portal.aws.amazon.com/billing/signup?redirect_url=https%3A%2F%2Faws.amazon.com%2Fregistration-confirmation#/start


## Install and configure the Amplify CLI
- Install  (Only new)
```sh
npm install -g @aws-amplify/cli
```

- Configure 
```sh
amplify configure
```
> Specify the AWS Region
> ? region:  eu-west-1
> Specify the username of the new IAM user:
> ? user name:  amplify-user
> Complete the user creation using the AWS console

https://console.aws.amazon.com/iam/home?region=eu-west-1#/users$new?step=final&accessKey&userNames=learn-aws-amplify&permissionType=policies&policies=arn:aws:iam::aws:policy%2FAdministratorAccess-Amplify

> Enter the access key of the newly created user:
> ? accessKeyId:  AKIARJVDYJHBUJB5XT7I
> ? secretAccessKey:  mFtucC+ojm7d1XRpG95eDrXDOYgz1YIvesJ+pvfP
> This would update/create the AWS Profile in your local machine
> ? Profile Name:  # (default)
> Successfully set up the new user.

# Set up fullstack project
## Create app
- Create a new JavaScript app
```sh
mkdir -p amplify-js-app/src && cd amplify-js-app
touch package.json index.html webpack.config.js src/app.js
```

- Replace following files with [this project](./assets/amplify-js-app/) : package.json, index.html, webpack.config.js

- Install dependencies
```sh
npm install
```

- Run app webpack
```sh
npm start
```

## Intialise amplify project
```sh
amplify init
Enter a name for the project (amplifyjsapp)

# All AWS services you provision for your app are grouped into an "environment"
# A common naming convention is dev, staging, and production
Enter a name for the environment (dev)

# Sometimes the CLI will prompt you to edit a file, it will use this editor to open those files.
Choose your default editor

# Amplify supports JavaScript (Web & React Native), iOS, and Android apps
Choose the type of app that you're building (javascript)

What JavaScript framework are you using (none)

Source directory path (src)

Distribution directory path (dist)

Build command (npm run-script build)

Start command (npm run-script start)

# This is the profile you created with the `amplify configure` command in the introduction step.
Do you want to use an AWS profile
```

# Connect API and database to the app
- Create graphql api and database
```sh
amplify add api
? Please select from one of the below mentioned services:
# GraphQL
? Provide API name:
# amplifyjsapp
? Choose the default authorization type for the API:
# API Key
? Enter a description for the API key:
# todos
? After how many days from now the API key should expire:
# 7 (or your preferred expiration)
? Do you want to configure advanced settings for the GraphQL API:
# No
? Do you have an annotated GraphQL schema?
# No
? Choose a schema template:
# Single object with fields (e.g., “Todo” with ID, name, description)
? Do you want to edit the schema now?
# Yes
```
will open amplify/backend/api/amplifyjsapp/schema.graphql

- deploy
```sh
amplify push
```

- check status
```sh
amplify status
```

- Test API
```sh
amplify console api
```

# Host app
- adding host
```sh
amplify add hosting
```

- publish app
```sh
 amplify publish
```

- See result
```sh
 amplify console
```

- Delete ALL
```sh
 amplify delete
```

- Check Delete
```sh
 amplify status
```