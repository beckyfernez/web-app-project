# Web App Project - Georgetown Campus Dining Reviews Web App

A Completed Repository for the [The Self-Directed "Freestyle" Project](https://github.com/prof-rossetti/intro-to-python/tree/main/projects/freestyle).

## Prerequisites

  + Anaconda 3.7+
  + Python 3.7+
  + Pip

## Installation

Optionally fork this [remote repository](https://github.com/beckyfernez/web-app-project), to create a copy under your own control. Then "clone" or download the remote repository (or your forked copy) onto your local computer, for example to your Desktop. Then navigate to wherever you downloaded the repo:

```sh
cd ~/Desktop/python/web-app-project
```

Use Anaconda to create a new virtual environment, perhaps called "dining-reviews-env":

```sh
conda create -n dining-reviews-env python=3.8
```

Activate your new virtual environment:

```sh
conda activate dining-reviews-env
```
OR, if your shell is not properly configured to use 'conda activate', use the following [workaround](https://github.com/conda/conda/issues/7980):

```sh
source activate dining-reviews-env
```

Then, within an active virtual environment, install package dependencies:

```sh
pip install -r requirements.txt
```

## Configuration

First, you will need to create and download Google API credentials. To do so, follow the instructions below:

Visit the [Google Developer Console](https://console.cloud.google.com). Create a new project, or select an existing one. Click on your project page, and then search for the "Google Sheets API" and enable it. Next, search for the "Google Drive API" and also enable it.

From the API page, or from the [API Credentials](https://console.cloud.google.com/apis/credentials) page, specifically manage the Google Drive API by creating your own credentials:

  1.  Click "Create Credentials" for a "Service Account". Follow the prompt to create a new service account named something like "spreadsheet-service":

    1.  What API are you using? > Google Drive API
    2.  Where will you be calling your API from? > Web Server
    3.  What data will you be accessing? > Application Data
    4.  Select Role > Basic > Editor

  2.  Click the newly created service account from the "Credentials" section, and click "Add Key" to create a new "JSON" credentials file for that service account. Download the resulting .json file (this might happen automatically).

  3.  Rename the file "google-credentials.json". Then move the copy of the json credentials file into the root directory of this repo and replace the json file name in the following python files: "review_submit.py" and "reviewaggregation.py". The change occurs in the following line of code:

  ```sh
  CREDENTIALS_FILEPATH = os.path.join(os.path.dirname(__file__),"..", "google-credentials.json")
  ```


Next, utilize the locations and review data stored on our ready-made google workbook at the following [link](https://docs.google.com/spreadsheets/d/1ciNHuyNCIMAYaBFQDNCykwwdWVEZwr2Uo8TnkHcO2Qg/edit#gid=615464139). 
> NOTE: You may also create your own data workbook imitating the template linked above, with the same sheet names and column headers. 

Lastly, create a '.env' file in your project repository. Then copy and paste the following environment variable:

```sh
# this is the ".env" file... with environment variables

# this is your google sheet specific API key in the url
GOOGLE_SHEET_ID="1ciNHuyNCIMAYaBFQDNCykwwdWVEZwr2Uo8TnkHcO2Qg"
```
> NOTE: If you created your own google workbook, as mentioned in the previous step, replace the environment variable with the appropriate value. 


# Testing

Run tests:

```sh
pytest
```

## Server Commands

Now, you're ready to see your new website! Run the following code in terminal to run the web app on your local computer:
```sh
FLASK_APP=web_app flask run
#or store the FLASK_APP=web_app in your .env file and then you can just enter 'flask run'
```

Run the following code in terminal to shut down your local server:
```sh
^C
```

## [Deploying](/DEPLOYING.md)

If you want to run the web app without your local server, follow the deployment instructions to deploy the app to a remote server. 

## Remote Web App

Visit your web app using the Heroku generated url. Your url may look like this:

```sh
https://dining-location-reviews-app.herokuapp.com/
```
Disclaimer: the url above is just a sample and is not functional!

Now, your home page should look something like this:


## [License](/LICENSE.md)

Copyright (c) 2015-2022 [Rebecca Fernandez](mailto:rmf83@georgetown.edu).
