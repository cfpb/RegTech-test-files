## How to interpret these files

- Each folder contains output of the [Mock Data Generator](https://github.com/cfpb/regtech-mock-data-generator) for a specific project (e.g. sbl).
- This repo assumes you have some kind of validator that accepts inputs of CSVs (e.g. [SBL's data validator](https://github.com/cfpb/regtech-data-validator)).
- Within each folder, you may find subfolders with categories of errors, but ultimatley, you should find a series of CSVs with the following naming schemas.

  - [project name]_[number of rows]_clean.csv: Should be a fake table that generates no errors with the specified number of rows. 
  - [project name]_[error name].csv: This should be a fake table that guarantees a triggering of the specified error. **NOTE: it does not mean that it only triggers that error, other errors might occur**
  
