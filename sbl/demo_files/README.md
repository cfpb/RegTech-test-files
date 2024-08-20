## Demo test files

For use in the beta for the Small Business Lending Filing Platform only, validation methods are subject to change. 

#### Filing platform overview 

![a screen capture of the stages of filing submission from within the beta for the Small Business Lending Data Filing Platform](filing-overview.png)

These are files that are designed to be used to explore different testing scenarios on the beta for the Small Business Lending Data Filing Platform and to help users navigate through different stages of the platform. 

1. Upload file
    - Select an appropriate .csv file for upload. 
    - Once it has uploaded, an upload summary will appear and validation check messages will be displayed. 
    - There may be errors, warnings, or neither in your file. Click continue to next step to view errors and warnings and to continue through the filing process.
2. Resolve errors
    - There are two types of errors that can occur in a file: syntax and logic. 
    - **Syntax errors** indicate that the data are improperly formatted and that the validation engine cannot evaluate if the data are within expected logical values.
    - **Logic errors** indicate that while the data are correctly formatted, there are missing or incorrect data or conflicting information in the file. 
    - There are two stages of error validation. First, syntax errors are identified and displayed on a page labeled **Resolve errors (syntax)**. Syntax errors must be resolved before the validation engine can progress to logic errors.  
    - Then, logic errors are identified and displayed on a page labeled **Resolve errors (logic)**. 
    - All syntax and logic errors must be resolved before you can progress in the platform to the **Review warnings** page. 
3. Review warnings
    - The **Review warnings** page provides an overview of any warning validations that were triggered by the uploaded file. 
    - **Warnings do not mean that your data are incorrect**, only that some values fall outside of generally expected ranges.  
    - You can either verify that the data are correct and continue, or go back to your file to make corrections, reupload, and continue. 
4. Provide point of contact
5. Sign and submit


#### Syntax errors
1. [**errors-page-1-syntax-few.csv:**](https://github.com/cfpb/regtech-test-files/blob/main/sbl/demo_files/errors-page-1-syntax-few.csv) This file contains records with syntactical errors that will trigger error validations that **will not** let you progress further through the beta filing experience. Syntactical errors indicate that the data are improperly formatted and that the validation engine cannot evaluate if the data are within expected logical values.
    - In this case, the syntactical error is [E0020](https://www.consumerfinance.gov/data-research/small-business-lending/filing-instructions-guide/2024-guide/#4.1.3): "'Application date' must be a real calendar date using YYYYMMDD format."
    - One record that contained an issue shows an Application date of 12012024, which is not a real calendar date following YYYMMDD format. 
    - This is a syntactical error because the formatting is incorrect. In contrast, an analogous logical error would be if the format were correct, 20241201 (December 1, 2024), but subsequently the Action taken date were listed as 20241131 (November 31, 2024), because an action cannot be taken before an application is submitted. 

2. [**errors-page-1-syntax-many.csv:**](https://github.com/cfpb/regtech-test-files/blob/main/sbl/demo_files/errors-page-1-syntax-many.csv) This file is similar to the previous file, but has many more examples of syntactical errors.


#### Logic errors

1. [**errors-page-2-logic-few.csv:**](https://github.com/cfpb/regtech-test-files/blob/main/sbl/demo_files/errors-page-2-logic-few.csv) This file contains records with logical errors that will trigger error validations that **will not** let you progress further through the beta filing experience. Logical errors indicate that while the data are correctly formatted, there are missing data, incorrect data, or conflicting information in the file. 
    - In this case, the file passes all syntactical error validation checks.
    - The logical errors are multi-field errors. The first one is [E0121](https://www.consumerfinance.gov/data-research/small-business-lending/filing-instructions-guide/2024-guide/#4.2.1): "'Type of guarantee' must contain at least one and at most five values, separated by semicolons."
    - This is a logical error because while the formatting is correct (999 separated by semicolons are  values), the values violate the logical rules set forth in the [Filing Instructions Guide entry for the Type of guarantee field](https://www.consumerfinance.gov/data-research/small-business-lending/filing-instructions-guide/2024-guide/#ct_guarantee).

2. [**errors-page-2-logic-many.csv:**](https://github.com/cfpb/regtech-test-files/blob/main/sbl/demo_files/errors-page-2-logic-many.csv) This file is similar to the previous file, but has many more examples of logical errors.

#### Warnings

1. [**warnings-page-few.csv:**](https://github.com/cfpb/regtech-test-files/blob/main/sbl/demo_files/warnings-page-few.csv) This file contains records with unexpected values that will trigger warning validations that **will** let you progress further through the beta filing experience. Warnings indicate that while data are correctly formatted and do not contain impossible values, they are expressing values that are outside the expected range for that field. These values may be correct, but these are warnings that you may want to take a look at the records and confirm this. 
    - In this case, the file passes all syntactical and logical error checks. 
    - One warning that appears is [W0182](https://www.consumerfinance.gov/data-research/small-business-lending/filing-instructions-guide/2024-guide/#4.4.4): "When present, 'loan term' should be less than 1200 (100 years)."
    - This is a warning because the loan term entered for that record is 1300 (108.335 years).
    - While this could potentially be correct, it is highly unlikely. Therefore, a warning is presented for you to go back and inspect your data. If you determine the data are correct, you can check the box to verify flagged register values and continue to the next step in the beta filing platform.

2. [**warnings-page-many.csv:**](https://github.com/cfpb/regtech-test-files/blob/main/sbl/demo_files/warnings-page-many.csv) This file is similar to the previous file, but has many more examples of warnings.

#### No errors or warnings 

1. [**edit-before-upload-no-errors-or-warnings.csv:**](https://github.com/cfpb/regtech-test-files/blob/main/sbl/demo_files/edit-before-upload-no-errors-or-warnings.csv) This file contains a single record that will not trigger any error or warning validation checks if you prepare it correctly. **It is titled 'edit-before-upload-no-errors-or-warnings.csv' because you must edit it before upload to receive no errors or warnings.**
    - The UID here is called "REPLACETHISUIDWITHYOUROWNUIDFORTHETEST". 
    - Edit the .csv and replace this UID with an example UID using your institution's own LEI to avoid Warning [W0003](https://www.consumerfinance.gov/data-research/small-business-lending/filing-instructions-guide/2024-guide/#4.4.1). 

## How to Download Files From This Repository for Use

To download files from this GitHub repository web page for use, click on the file listed in the repo:

![a screenshot of a pointer hovering over a .csv file in the repo, part of the instructions for downloading](https://github.com/cfpb/regtech-test-files/blob/main/download-instructions-1.png)

Once the file is opened in GitHub in the browser, click on the Download raw file button in the upper right hand corner of the table display (shown in yellow): 

![a screenshot of the Download raw file button for a .csv file in the repo, part of the instructions for downloading](https://github.com/cfpb/regtech-test-files/blob/main/download-instructions-2.png)

Repeat this process for any individual files that you would like to download for testing with the beta for the Small Business Lending Data Filing Platform. 

You may also download this entire repo as a ZIP file by clicking Download ZIP from the Code menu button on the main page of this repo:

![a screenshot of a pointer hovering over the Download ZIP button for the repo, part of the instructions for downloading](https://github.com/cfpb/regtech-test-files/blob/main/download-instructions-3.png)
