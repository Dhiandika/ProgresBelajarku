# Dhiandika TOD

# API Reference

## All Items

#### Get all items

```
  GET {{server}}/
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |

#### Delete item

```
  DEL {{server}}/
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | **Required**. Id of item to fetch |


###
## Users
#### Get All Users
```
  GET {{server}}/users
```
#### Get All Users by Id
```
  GET {{server}}/users/{{idUser}}
```
#### Add Users
```
  POST {{server}}/users
```
#### Update Users by Id
```
  PUT {{server}}/users/{{idUser}}
```
#### Delete Users by Id
```
  DEL {{server}}/users/{{idUser}}
```
###
## Articel
#### Get All Articel
```
  GET {{server}}/Articel
```
#### Get All Articel by Id
```
  GET {{server}}/Articel/{{idArticel}}
```
#### Add Articel
```
  POST {{server}}/Articel
```
#### Update Articel by Id
```
  PUT {{server}}/Articel/{{idArticel}}
```
#### Delete Articel by Id
```
  DEL {{server}}/Articel/{{idArticel}}
```
###

## Deploying to Cloud Run
- ### Preconditions
  Before deploying your app to Google Cloud Run, ensure that you meet the following prerequisites:
  - Create a Google Cloud Platform (GCP) account and manage projects.
  - Install and configure the Google Cloud SDK on your local machine.
  Please note that "prerequisites" is a plural noun, so it is more appropriate to use "meet the following prerequisites" instead of "meet the following prerequisite" in this context.

- ### Steps
  - Prepare the application
    Ensure that your application is ready for deployment on Google Cloud Run. This involves conducting local testing and ensuring that the necessary configuration is in place.
  - Create a container image
    Google Cloud Run requires the application to be packaged as a distributable container image. Build container images of your applications using tools like Docker.
  - Upload the container image
    Upload the container image you created to the Google Container Registry (GCR) using the gcloud command. Before proceeding, ensure that you are signed in to the correct Google Cloud Platform (GCP) account.
    Example command to upload a container image:
    ```
    gcloud builds submit --tag gcr.io/[PROJECT-ID]/[IMAGE-NAME]
    ```
  - Deploy to Google Cloud Run
    Use the gcloud run deploy command to deploy your application to Google Cloud Run. Specify the service name, select the uploaded container image, and configure any additional options as necessary.
    Example command to deploy an application to Google Cloud Run:
    ```
    gcloud run deploy [SERVICE-NAME] --image gcr.io/[PROJECT-ID]/[IMAGE-NAME] --platform managed
    ```
  - Accessing the application
    After the deployment process is complete, you will receive a URL that provides access to the deployed application. Utilize this URL to access the app through a web browser or by employing an API testing tool such as cURL or Postman.
