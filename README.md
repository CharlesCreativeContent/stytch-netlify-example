# Stytch Netlify example application

<p align="center">
  <img src="https://user-images.githubusercontent.com/100632220/217049841-b9eeb72a-3e50-4074-839a-e64ee5d4a88c.png" width="750">
</p>

## Overview

This example application demonstrates how one may use Stytch within a Next.js application running on [Netlify](https://www.netlify.com/integrations/stytch/).

This project uses Stytch's [Next.js SDK](https://stytch.com/docs/sdks/javascript-sdk) which provides pre-built UI components, useful React hooks, headless methods to securely interact with Stytch, and is SSR friendly. This project also utilizes Stytch's [Node Backend SDK](https://www.npmjs.com/package/stytch) for authenticating the logged in user's session.  

This application features Email Magic Links and Google OAuth authentication. You can use this application's source code as a learning resource, or use it as a jumping off point for your own project. We are excited to see what you build with Stytch!

## Set up

Follow the steps below to get this application fully functional and running using your own Stytch credentials.

### In the Stytch Dashboard

1. Create a [Stytch](https://stytch.com/) account. Once your account is set up a Project called "My first project" will be automatically created for you.

2. Within your new Project, navigate to [Frontend SDKs](https://stytch.com/dashboard/sdk-configuration), and make the following changes:

   - Click **Enable SDK**.
   - Under **Authorized applications** add the domain `http://localhost:8888`.

3. Navigate to [Redirect URLs](https://stytch.com/dashboard/redirect-urls), and add `http://localhost:8888/authenticate` as the types **Login** and **Sign-up**.

4. Navigate to [OAuth](https://stytch.com/dashboard/oauth), and set up login for Google in the Test environment. Follow all the instructions provided in the Dashboard. If you are not interested in OAuth login you can skip this step. However, the _Continue with Google_ button in this application will not work.
   
   <img width="400" alt="OAuth configuration" src="https://user-images.githubusercontent.com/100632220/217055674-a7dafc17-6ad3-492f-8dd2-92560d60dc00.png">

5. Finally, navigate to [API Keys](https://stytch.com/dashboard/api-keys). You will need the `project_id`, `secret`, and `public_token` values found on this page later on.

### Running the app
In your terminal clone the project and install dependencies:

```bash
git clone https://github.com/stytchauth/stytch-netlify-example
cd stytch-netlify-example
npm i
npm install netlify-cli -g
```

Next, create `.env.local` file by running the command below which copies the contents of `.env.template`. If you'd like to run the app via Netlify instead of locally, you can skip this step and head straight to the [Running the app on Netlify](#running-the-app-on-netlify) section.
```bash
cp .env.template .env.local
```

Open `.env.local` in the text editor of your choice, and set the environment variables using the `project_id`, `secret`, and `public_token` found on [API Keys](https://stytch.com/dashboard/api-keys). Leave the `STYTCH_PROJECT_ENV` value as `test`.

```
# This is what a completed .env.local file will look like
STYTCH_PROJECT_ENV=test
STYTCH_PROJECT_ID=project-test-00000000-0000-1234-abcd-abcdef1234
NEXT_PUBLIC_STYTCH_PUBLIC_TOKEN=public-token-test-abcd123-0000-0000-abcd-1234567abc
STYTCH_SECRET=secret-test-12345678901234567890abcdabcd
```

## Running the app on Netlify
Click the button below to deploy this application to Netlify. This will create a new Netlify site and deploy the application to it. You will be prompted to enter your Stytch [API Keys](https://stytch.com/dashboard/api-keys). 

Note, you'll need to add your Netlify's site domain to the [Redirect URLs](https://stytch.com/dashboard/redirect-urls), e.g. `https://main--wonderful-salmiakki-f95458.netlify.app/authenticate`, and [Authorized applications](https://stytch.com/dashboard/sdk-configuration) in your Stytch Dashboard, e.g. `https://main--wonderful-salmiakki-f95458.netlify.app`. 

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/stytchauth/stytch-netlify-example)
<br id="netlify">
## Running the app locally
If you want to run the app locally, the app may be run with the command:

```bash
netlify dev
```

The application will be available at [`http://localhost:8888`](http://localhost:8888).

You'll be able to login with Email Magic Links or Google OAuth and see your Stytch User object, Stytch Session, and see how logging out works.

## Next steps

This example app showcases a small portion of what you can accomplish with Stytch. Here are a few ideas to explore:

1. Add additional login methods like [Passwords](https://stytch.com/docs/passwords#guides_getting-started-sdk).
2. Replace the prebuilt UI with your own using by using the SDK's [headless methods](https://stytch.com/docs/sdks/javascript-sdk).
3. Replace the Google OAuth button with the high converting [Google One Tap UI](https://stytch.com/docs/oauth#guides_google-sdk).
4. Secure your app further by building MFA authentication using methods like [WebAuthn](https://stytch.com/docs/sdks/javascript-sdk#webauthn).

## Get help and join the community

#### :speech_balloon: Stytch community Slack

Join the discussion, ask questions, and suggest new features in our ​[Slack community](https://join.slack.com/t/stytch/shared_invite/zt-nil4wo92-jApJ9Cl32cJbEd9esKkvyg)!

#### :question: Need support?

Check out the [Stytch Forum](https://forum.stytch.com/) or email us at [support@stytch.com](mailto:support@stytch.com).
