# Build a landing page using Strapi and HTML

![Cover](https://res.cloudinary.com/craigsims808/image/upload/v1751544336/strapi/strapi-landing/cover_ljxbze.png)

## Description

This repo serves as a code container for the article: [Build a landing page using Strapi and HTML](https://dev.to/markmunyaka/build-a-landing-page-using-strapi-and-vanilla-html-pl0)

## Prerequisites

To test out the source code you will need:
- [Node.js LTS (v18, v20 or v22)](https://nodejs.org/)
- GitHub/GitLab/Google Account to create a Strapi Cloud Account

## Getting Started

Clone the repo.
```shell
git clone https://github.com/Marktawa/strapi-landing
```

## Strapi Setup

Install the dependencies.
```shell
cd strapi-landing/backend && npm install
```

Set up Environment variables
```shell
cp .env.example .env
```

Create admin user. *For example one with email `chef@strapi.io` and password `Gourmet1234`.*
```shell
npm run strapi admin:create-user -- --firstname=Kai --lastname=Doe --email=chef@strapi.io --password=Gourmet1234
```

Run Strapi server.
```shell
npm run develop
```

Login to your Strapi admin by visiting [localhost:1337/admin](http://localhost:1337/admin) using the admin email and password you created earlier.

![Strapi Admin Login](https://res.cloudinary.com/craigsims808/image/upload/v1737184283/strapi/strapi-railway/strapi-admin-login_mxcmfn.png)

Clicking on **Login** gives you the Strapi Admin Dashboard Home page:

![Strapi Admin Dashboard Home Page](https://res.cloudinary.com/craigsims808/image/upload/v1738201442/strapi/strapi-next-auth/strapi_admin_ja7t4h.png)

### Test API

In a separate terminal session run the following command to create a new Contact
```shell
curl -X POST \
  http://localhost:1337/api/contacts \
  -H "Content-Type: application/json" \
  -d '{
    "data": {
      "Name": "John Doe",
      "Email": "john@example.com",
      "Message": "This is a test message"
    }
  }'
```

You should see a JSON response similar to this:
```json
{
    "data": {
        "id": 1,
        "documentId": "ghn77cyweudup0o1wtpcr8ku",
        "Name": "John Doe",
        "Email": "john@example.com",
        "Message": "This is a test message",
        "createdAt": "2025-07-03T08:42:44.306Z",
        "updatedAt": "2025-07-03T08:42:44.306Z",
        "publishedAt": "2025-07-03T08:42:44.289Z"
    },
    "meta": {}
}
```

Verify that the contact was saved by checking your Strapi Admin Panel. Visit the **Content Manager** section and click **Collection types** then **Contacts** then view the entries.

![Contact entry in Content Manager](https://res.cloudinary.com/craigsims808/image/upload/v1751532292/strapi/strapi-landing/verify-contact-in-Strapi-admin_xrynav.png)

## Frontend setup

Open up your project folder, `strapi-landing` in a new terminal session:
```shell
cd strapi-landing
```

Open the `frontend` folder for your landing page:
```shell
cd frontend
```

Launch the frontend for testing:
```shell
python -m http.server
```

View landing page in your browser and test the contact form.
![Updated local landing page](https://res.cloudinary.com/craigsims808/image/upload/v1751535693/strapi/strapi-landing/landing-page-full-screenshot-tinified_hgo4ar.png)

## Author

Mark Munyaka  
[dev.to/markmunyaka](https://dev.to/markmunyaka)


