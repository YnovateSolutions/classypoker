## Quick Start

### Set-up MongoDB

Set-up either a local mongoDB instance or create a [cloud-hosted instance](https://www.mongodb.com/). Save your db username + passsword and the mongoDb connection-string as you will need it for the next step.

### Add a "local.env" file in the "/server/config" folder with the following entries

```
  MONGO_URI=<YOUR_MONGODB_URI>
  JWT_SECRET=<YOUR_JWT_SECRET>
  PORT=<YOUR_SERVER_PORT>
  NODE_ENV=development
  SMTP_HOST=<YOUR_SMTP_HOST>
  SMTP_PORT=<YOUR_SMTP_PORT>
  SMTP_USER=<YOUR_SMTP_USER>
  SMTP_PW=<YOUR_SMTP_PASSWORD>
```

### Set-up Contentful

Create a free community [Contentful-Account](https://www.contentful.com/get-started/) and create a new Space. Add two locales (en, de) with "en" being the fallback for the german-locale. Create a Content Delivery API Key and copy your space token and Contentful Delivery API access-token to the clipboard, as you will need it for the next step.

You can use the [Contentful CLI](https://www.npmjs.com/package/contentful-cli) to import the space backup from the "contentful"-folder into your own Contentful space. This backup includes all localized key-value pairs and the content of the static pages.

### Add a ".env.local" file in the "/client" folder with the following entries

```
  REACT_APP_CONTENTFUL_SPACE_ID=<YOUR_CONTENTFUL_SPACE_ID>
  REACT_APP_CONTENTFUL_ACCESS_TOKEN=<YOUR_CONTENTFUL_ACCESS_TOKEN>
  REACT_APP_GOOGLE_ANALYTICS_TRACKING_ID=<YOUR_GOOGLE_ANALYTICS_TRACKING_ID>
  REACT_APP_SERVER_URI=<YOUR_BACKEND_URI_HOST_PORT>
```

### Install server dependencies

```bash
npm install
```

### Install client dependencies

```bash
cd client
npm install
```

### Run both Express & React from root project-directory

```bash
npm run dev
```

### Build for production

```bash
cd client
npm run build
```

### Test production before deploy

```bash
NODE_ENV=production node server.js
```
