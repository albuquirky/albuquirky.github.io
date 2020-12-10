# Build Instructions - Server Side

## Step One: Clone the GitHub Repository.

1. Navigate to the GitHub repository [here]().
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

1. This app requires some editing of the ```application.yml``` file in order to function. Within must be two values: ```client_id``` and ```base_url```.
    * The ```client_id``` must be set to a client ID in the Google Cloud Console.
    * The ```base_url``` must be set to the base URL from which your server will be operating. This will take the following form: ```http://[BASE URL]:[PORT]/albuquirky/api/```
        * The ```[BASE URL]``` will differ depending on whether you are operating on a physical device or an emulator. You can find the physical device URL through a command terminal, but an emulator will usually use ```10.0.2.2```.
        * The ```[PORT]``` represents the port through which traffic comes in and out of the server. This repository is using port ```8080```, but you can change this to any port you like by editing the ```server:port``` value in the ```application.yml``` file.