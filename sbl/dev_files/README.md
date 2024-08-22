## Dev files

These folders contain files that are mainly applicable to developers and those wanting to test specific details or aspects of the beta for the Small Business Lending Data Filing Platform. For general audiences wishing to test the beta for the Small Business Lending Data Filing Platform, please see the **demo_files** folder in this repo. 

Each folder contains output of the [Mock Data Generator](https://github.com/cfpb/regtech-mock-data-generator) for a specific project (e.g. sbl). These files can be used with the beta for the Small Business Lending Data Filing Platform or with the [data validator](https://github.com/cfpb/regtech-data-validator).

- The **single_field_errors** folder contains many .csv files that will produce all of the various single-field errors contemplated in the [Filing Instructions Guide](https://www.consumerfinance.gov/data-research/small-business-lending/filing-instructions-guide/2024-guide/#4.1). This file guarantees a triggering of the specified error. **NOTE: it does not mean that it only triggers that error, other errors might occur**

- The **multi_field_errors** folder contains many .csv files that will produce all of the various multi-field errors contemplated in the [Filing Instructions Guide](https://www.consumerfinance.gov/data-research/small-business-lending/filing-instructions-guide/2024-guide/#4.2). This file guarantees a triggering of the specified error. **NOTE: it does not mean that it only triggers that error, other errors might occur**

- The **no_errors_or_warnings** folder contains a .csv file of 100 records that will trigger no errors or warnings, except the UID must contain an LEI that matches the institution filing using the beta for the Small Business Lending Data Filing Platform. Edit the .csv and replace this UID with an example UID using your institution's own LEI to avoid Warning [W0003](https://www.consumerfinance.gov/data-research/small-business-lending/filing-instructions-guide/2024-guide/#4.4.1). 

## How to download files from this repository for use

To download files from this GitHub repository, click on the file listed in the repo:

![a screenshot of a pointer hovering over a .csv file in the repo, part of the instructions for downloading](https://github.com/cfpb/regtech-test-files/blob/main/download-instructions-1.png)

Once the file is opened in GitHub in the browser, click on the "Download raw file" button in the upper right hand corner of the table display:

![a screenshot of the Download raw file button for a .csv file in the repo, part of the instructions for downloading](https://github.com/cfpb/regtech-test-files/blob/main/download-instructions-2.png)

Repeat this process for any individual files that you would like to download for testing with the beta for the Small Business Lending Data Filing Platform.

You may also download this entire repo as a ZIP file by clicking "Download ZIP" from the "Code" menu button on the main page of this repo:

![a screenshot of a pointer hovering over the Download ZIP button for the repo, part of the instructions for downloading](https://github.com/cfpb/regtech-test-files/blob/main/download-instructions-3.png)
