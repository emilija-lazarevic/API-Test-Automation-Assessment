# API-Test-Automation-Assessment

# Prerequisites

To run these tests, you will need Postman.

The app can be downloaded here: https://www.postman.com/downloads/

Create a new account or login to your account if you have one.

# Importing the tests into Postman

Before running the tests, they will need to be imported to Postman.

To do that first you need to download the [API Test Automation Assessment.postman_collection.json](https://github.com/emilija-lazarevic/API-Test-Automation-Assessment/blob/Postman_Collection/test-scripts/API%20Test%20Automation%20Assessment.postman_collection.json) and the [Sandbox.postman_environment.json](https://github.com/emilija-lazarevic/API-Test-Automation-Assessment/blob/minor_updates_for_md_files/test-scripts/Sandbox.postman_environment.json) file. 

You can do that by opening the file and clicking on the download button:

![git-download-btn](https://github.com/emilija-lazarevic/API-Test-Automation-Assessment/assets/48448148/bddf7d7d-56e9-4f60-a68c-e8080ea951e3)



Open Postman, click on Workspaces in the top left corner, and select your workspace if you have one, or create a new one.

Once you have opened a workspace, you can import the test JSON fie. Click on the Import button which is right under the API Network menu in the top left corner:

![postman-import](https://github.com/emilija-lazarevic/API-Test-Automation-Assessment/assets/48448148/8e8b9e75-2ca6-41e0-977a-ee9bf8d99d02)


Select the previously downloaded API Test Automation Assessment.postman_collection.json file and it should be automatically imported.

Under the import button you will be able to see the test hirearchy:

![image](https://github.com/emilija-lazarevic/API-Test-Automation-Assessment/assets/48448148/0765f3ae-a59b-47c9-bc7f-221d51861461)


Tests are separated by the two roles (User and Admin) and each use case for that role has a separate folder with test scenarios related to them.

# Selecting the environment

Import the environment using the same steps that you used for importing tests, this time you need to import the Sandbox.postman_environment.json.

Check if the right environment is selected. In the top right corner, under you account avatar, there will be the environment dropdown:

![environment-menu](https://github.com/emilija-lazarevic/API-Test-Automation-Assessment/assets/48448148/af3b2e3c-3b0e-4334-84a3-74c64024e404)


If the environment is already selected, it will say Sandbox. If it is not selected, it will say No Enviornment, and you need to click on the dropdown menu and select Sandbox.

# Running the tests

First click on the 'Api Test Automation Assesment' in your workspace.

If you want to run the whole suite, you can click on the Run button that's located under the environment dropdown. A runner will open with a Run order list where you can choose which tests you want to run by ticking the checkboxes (by default they should all be selected). On the right side, there will be an orange button that says Run <collection name>, click on that and the suite will run.

To run certain tests, you need to tick checkboxes for those tests only and click on the Run button again.

Single tests can also be run by clicking on a request from your workspace:

![image](https://github.com/emilija-lazarevic/API-Test-Automation-Assessment/assets/48448148/3d2a9f94-7b54-483a-8471-e07ad90125ba)


Once the request opens, click on the Send button. In the bottom section of the screen, there will be a tab with test results for that request:

![image](https://github.com/emilija-lazarevic/API-Test-Automation-Assessment/assets/48448148/532a660f-0b85-4dde-82a4-7fde2c8fb209)

If you want to run all the tests for a role or for a use case, you just need to click on a desired folder and repeate the steps for running the entire suite.
