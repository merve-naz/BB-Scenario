## Step 3: Deploy the Go web application to Google Cloud Platform

In this step, you will deploy the Go web application you created in the previous step to the Google Cloud Platform. Here's how to do it:

1. Create a new project on the Google Cloud Platform and select a billing account.

2. Install the Google Cloud SDK by running the following command in your virtual terminal:

```
$ apk add --no-cache curl python3
$ curl https://sdk.cloud.google.com | bash
```
3. After installing the Google Cloud SDK, initialize it by running the following command:

```$ gcloud init```
This will prompt you to log in to your Google Cloud account and select the project you created in step 1.

4. Next, create a new App Engine application by running the following command:
```$ gcloud app create```

This will prompt you to select a region for your App Engine application.

5. Deploy your Go web application to the App Engine by running the following command:
```$ gcloud app deploy```
This will package and deploy your Go web application to the App Engine.

6. Finally, navigate to your deployed application by running the following command:
```$ gcloud app browse```
This will open a browser and navigate to the URL of your deployed application.

Congratulations! You have now deployed your Go web application to the Google Cloud Platform using the App Engine service.