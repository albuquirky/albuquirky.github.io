# Build Instructions - Server Side

## Step One: Clone the GitHub Repository.

1. Navigate to the GitHub repository [here](https://github.com/albuquirky/albuquirky-service).
2. In the very top-right corner of the screen, select "Fork."
3. Select the account or organization you would like to fork the repository to.
4. Once selected, GitHub will redirect you to the newly-created ```albuquirky-service``` repository in your organization or account.
5. Select the green "Code" button, then copy the link to clone the repository.

### Method One: Clone the Repository Manually

1. In a Git Bash terminal, navigate to the directory you wish to clone the repository into.
2. Once you are in the desired directory, enter the following command, replacing the placeholder with the link: ```git clone [LINK]```

### Method Two: Clone from IntelliJ IDEA

1. Open IntelliJ IDEA.
2. Instead of selecting a recent project from the left, select instead the "Get from Version Control" option.
3. Make sure that the "Repository URL" option on the left is selected.
4. Enter the link copied from the "Code" button earlier into the "URL" field.
5. Click the folder icon in the "Directory" field and navigate to the directory you would like to save the repository to.
6. Select "Clone."

## Step Two: Import the App into IntelliJ IDEA

***This step is unnecessary if you opted to clone the repository using IntelliJ instead of doing so manually.***

1. Once the repository has been cloned into your desired directory, open IntelliJ IDEA.
2. Instead of selecting a recent project from the left, select the "Open or Import" option.
3. Navigate to the directory you would like to save the repository to.
4. Select "OK."

## Step Three: Executing the Build

1. Open the app in IntelliJ, if it isn't already open.
2. This app requires some editing of the ```application.yml``` file in order to function - particularly, the  ```client_id``` file.
    * The ```spring:security:oauth2:resourceserver:jwt:issuer-uri``` must be set to ```https://accounts.google.com```.
    * The ```spring:security:oauth2:resourceserver:jwt:client-id``` must be set to a client ID in the Google Cloud Console. One must be set up on your Cloud Console project's OAuth 2.0 client IDs section under Credentials for each device accessing the application. More information can be found [here](https://support.google.com/googleapi/answer/6158862?hl=en).
3. Navigate to the ```AlbuquirkyApplication``` class along the path ```src\main\java\edu\cnm\deepdive\albuquirky```.
4. Launch the ```main``` method.