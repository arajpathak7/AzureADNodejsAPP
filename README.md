# How to run the completed project
Clone the Repo to your local folder. You can open the local folder in Visual Studio to view the code.
## This project shows, how to receive Azure Active Directory token. It then uses the token to get user profile details from Azure AD by using Microsoft Graph

## Prerequisites

To run the completed project in this folder, you need the following:

- [Node.js](https://nodejs.org) installed on your development machine. If you do not have Node.js, visit the previous link for download options. (**Note:** This tutorial was written with Node version 10.7.0 and above. The steps in this guide may work with other versions, but that has not been tested.)
- You can [sign up for the Office 365 Developer Program](https://developer.microsoft.com/office/dev-program) to get a **free Office 365 subscription**. {The process will help you create a Global Administrator account for the respective Azure AD tenant.}

## Register a web application with the Azure Active Directory Portal

1. Open a browser and navigate to the [Azure Active Directory Portal](https://aad.portal.azure.com). Login using above created Office 365 Admin account or **personal account** (aka: Microsoft Account) or **Work or School Account**.

1. Select **Azure Active Directory** in the left-hand navigation, then select **App registrations** under **Manage**.

1. Select **New registration**. On the **Register an application** page, set the values as follows.

    - Set **Name** to `Node.js App`.
    - Set **Supported account types** to **Accounts in any organizational directory and personal Microsoft accounts**.
    - Under **Redirect URI**, set the first drop-down to `Web` and set the value to `http://localhost:3000/auth/callback`.

1. Choose **Register**. On the **Node.js App** page, copy the value of the **Application (client) ID** and save it, you will need it in the next step.

1. Select **Authentication** under **Manage**. Locate the **Implicit grant** section and enable **ID tokens**. Choose **Save**.

1. Select **Certificates & secrets** under **Manage**. Select the **New client secret** button. Enter a value in **Description** and select one of the options for **Expires** and choose **Add**.

1. Copy the client secret value before you leave this page. You will need it in the next step.

    > [!IMPORTANT]
    > This client secret is never shown again, so make sure you copy it now.

## Configure the sample

1. Rename the `.env.example` file to `.env`.
1. Edit the `.env` file and make the following changes.
    1. Replace `YOUR_APP_ID_HERE` with the **Application Id** you got from the App Registration Portal.
    1. Replace `YOUR_APP_PASSWORD_HERE` with the password you got from the App Registration Portal.
1. In your command-line interface (CLI), navigate to this directory and run the following command to install requirements.

    ```Shell
    npm install
    ```

## Run the sample

1. Run the following command in your CLI to start the application.

    ```Shell
    npm start
    ```

1. Open a browser and browse to `http://localhost:3000`.
