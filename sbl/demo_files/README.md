# Demo files

These folders contain test files that can be used by general audiences wishing to test the beta for the Small Business Lending Platform. These files are for use in the beta for the Small Business Lending Filing Platform only, validation methods are subject to change. 

For developers and those wanting to test specific details or aspects of the beta for the Small Business Lending Data Filing Platform, please see the **[dev files](https://github.com/cfpb/RegTech-test-files/tree/6359bc53119b29ecc4ee16ca4df59c1c17af514f/sbl/dev_files)** folder in this repo. 

Page sections:
- [Filing platform overview](#filing-platform-overview)
- [Test file descriptions](#test-file-descriptions)
- [How to download files from this repository](#how-to-download-files-from-this-repository)

## Filing platform overview 

<img width="1216" alt="a screen capture of the steps of the filing process from within the beta for the Small Business Lending Data Filing Platform" src="https://github.com/user-attachments/assets/34d78c7c-12f9-445b-aaea-c5a1b589ea9c">

### Step 1. Upload file
- Select an appropriate .csv file for upload 
- Once your file is successfully uploaded and validation checks are performed, an upload summary will display upload status and validation check results 
  - There may be errors, warnings, or neither in your file
- Navigate to the next step to review the results of the validation checks and continue with the filing process

### Step 2. Resolve errors
- There are two types of errors that can occur in a file:
    - **Syntax errors** indicate that the data are improperly formatted. We are unable to detect errors or warnings related to logic until your register passes these checks.
    - **Logic errors** indicate that while the data are correctly formatted, there are missing or incorrect data or conflicting information in the register. Your register must pass these checks to continue to the next step. 
- There are two error validation phases:
  - First, syntax errors are identified and displayed on a page labeled **Resolve errors (syntax)**.  We are unable to detect errors or warnings related to logic until your register passes these syntax checks.  
  - Then, logic errors are identified and displayed on a page labeled **Resolve errors (logic)** 
- Your register must pass both syntax and logic checks to continue to the **Review warnings** step

### Step 3. Review warnings
- The **Review warnings** step displays an overview of register values flagged by warning validations
- **Warnings do not mean that your data are incorrect**, only that some values fall outside of generally expected ranges  
- You can either verify the accuracy of register values flagged by warning validations and continue, or go back to your file to make corrections, upload a new file, and continue through the filing process 

### Step 4. Provide point of contact

### Step 5. Sign and submit

## Test file descriptions
These files can be used to explore different testing scenarios on the beta for the Small Business Lending Data Filing Platform and to help users navigate through different steps of the filing process. 

### Errors (syntax)
1. [**errors-page-1-syntax-few.csv:**](https://github.com/cfpb/regtech-test-files/blob/main/sbl/demo_files/errors-page-1-syntax-few.csv) This file contains records with errors related to data type and format that **will not** let you progress further through the beta filing process. Errors in syntax indicate that the data are improperly formatted such that our system is unable to check for consistent and accurate logic in your register.
    - In this case, the error is [E0020](https://www.consumerfinance.gov/data-research/small-business-lending/filing-instructions-guide/2024-guide/#4.1.3): "'application date' must be a real calendar date using YYYYMMDD format."
    - One record that contained an issue shows an 'application date' of 12012024, which is not a real calendar date following YYYMMDD format. 
    - This is an error in syntax because the formatting is incorrect. In contrast, an analogous error in logic would be if the format were correct, 20241201 (December 1, 2024), but subsequently the 'action taken date' were listed as 20241131 (November 31, 2024), because an action cannot be taken before an application is submitted. 

2. [**errors-page-1-syntax-many.csv:**](https://github.com/cfpb/regtech-test-files/blob/main/sbl/demo_files/errors-page-1-syntax-many.csv) This file is similar to the previous file, but has many more examples of errors in syntax.


### Errors (logic)
1. [**errors-page-2-logic-few.csv:**](https://github.com/cfpb/regtech-test-files/blob/main/sbl/demo_files/errors-page-2-logic-few.csv) This file contains records with errors in logic that will trigger error validations that **will not** let you progress further through the beta filing process. Errors in logic indicate that while the data are correctly formatted, your register contains inconsistent or inaccurate values.
    - In this case, the file passes all errors in syntax
    - The errors in logic are multi-field errors. The first one is [E0121](https://www.consumerfinance.gov/data-research/small-business-lending/filing-instructions-guide/2024-guide/#4.2.1): "'type of guarantee' must contain at least one and at most five values, separated by semicolons."
    - This is an error in logic because while the formatting is correct (999 separated by semicolons are  values), the values violate the logical rules set forth in the [filing instructions guide entry for the 'type of guarantee' field](https://www.consumerfinance.gov/data-research/small-business-lending/filing-instructions-guide/2024-guide/#ct_guarantee).

2. [**errors-page-2-logic-many.csv:**](https://github.com/cfpb/regtech-test-files/blob/main/sbl/demo_files/errors-page-2-logic-many.csv) This file is similar to the previous file, but has many more examples of errors in logic.

### Warnings
1. [**warnings-page-few.csv:**](https://github.com/cfpb/regtech-test-files/blob/main/sbl/demo_files/warnings-page-few.csv) This file contains records with unexpected values that will trigger warning validations that **will** let you progress further through the beta filing process. Warnings indicate that while data are correctly formatted and do not contain impossible values, they contain values that are outside the expected range for that field. If warnings are found, review the tables below or download the validation report (CSV) to determine if the values flagged with warning validations require action.
    - In this case, the file contains no errors but does contain warnings 
    - One warning that appears is [W0182](https://www.consumerfinance.gov/data-research/small-business-lending/filing-instructions-guide/2024-guide/#4.4.4): "When present, 'loan term' should be less than 1200 (100 years)."
    - This is a warning because the loan term entered for that record is 1300 (108.335 years)
    - While this could potentially be correct, it is highly unlikely. Therefore, the value is flagged by a warning validation and you can go back and inspect your data. If you determine the data are correct, you can verify the accuracy of register values flagged by warning validations and continue to the next step in the filing process.

2. [**warnings-page-many.csv:**](https://github.com/cfpb/regtech-test-files/blob/main/sbl/demo_files/warnings-page-many.csv) This file is similar to the previous file, but has many more examples of warnings.

### No errors or warnings 

1. [**edit-before-upload-no-errors-or-warnings.csv:**](https://github.com/cfpb/regtech-test-files/blob/main/sbl/demo_files/edit-before-upload-no-errors-or-warnings.csv) This file contains a single record that will not trigger any error or warning validations if you prepare it correctly. **It is titled 'edit-before-upload-no-errors-or-warnings.csv' because you must edit it before upload to receive no errors or warnings.**
    - The UID here is called "REPLACETHISUIDWITHYOUROWNUIDFORTHETEST" 
    - Edit the .csv and replace this UID with an example UID using your institution's own Legal Entity Identifier (LEI) to avoid Warning [W0003](https://www.consumerfinance.gov/data-research/small-business-lending/filing-instructions-guide/2024-guide/#4.4.1) 

## How to download files from this repository

To download files from this GitHub repository, click on the file listed in the repo:

<img width="424" alt="a screenshot of a pointer hovering over a .csv file in the repo, part of the instructions for downloading" src="https://github.com/user-attachments/assets/2b28f446-985b-4faf-95b6-c6ee58d04cb6">

Once the file is opened in GitHub in the browser, click on the "Download raw file" button in the upper right hand corner of the table display (shown in green): 

<img width="281" alt="a screenshot of the Download raw file button for a .csv file in the repo, part of the instructions for downloading" src="https://github.com/user-attachments/assets/2628c976-6990-4021-aa2a-47f29f3f1460">

Repeat this process for any individual files that you would like to download for testing with the beta for the Small Business Lending Data Filing Platform. 

You may also download this entire repo as a ZIP file by clicking "Download ZIP" from the "Code" menu button on the [main page](https://github.com/cfpb/RegTech-test-files) of this repo:

<img width="524" alt="a screenshot of a pointer hovering over the Download ZIP button for the repo, part of the instructions for downloading" src="https://github.com/user-attachments/assets/e37a9aab-6528-4078-a1a7-0a6d575c76db">
