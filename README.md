STEP BY STEP LOAD PROCESS:

STEP 1: Declaring variable we declare the variables filename and fileid locally in the processingfiles. 

STEP 2: checking whether the filename is present in the processingfiles or not if not exists we          insert the file into processingfiles marks the file as `"Pending".it prevents duplicate entries for same file.
STEP 3: Dropping and creating the tempfile.

STEP 4: Loading textfile into the tempfile by using Bulk load. 

STEP 5: Checking the members in tempfile who are not of gender in M or f.

STEP 6: Update gender in tempfile from DB who are not having gender in M or F by joining the members table memberid and the memberid from file. 

STEP 7: Update gender in tempfile from DB who are not having gender in M or F by joining the members table memberid and the memberid from file by replacing the first 3 characters of memberid from file if they are not numeric

STEP 10: Insert temp-file Data into Main Table LabFileData.

STEP 11:  Update patientid in labfile data by trimming leading and ending spaces in patientid.

STEP 12: Update memberid in labfiledata from DB whose memberid is null by joining   members memberid with patientid from file and removing the first three characters if they are not numeric in patientid.

STEP 13: Update memberid in labfiledata from DB whose memberid is null by joining   members memberid with patientid from file.

STEP 14: Update memberid in labfiledata from DB whose memberid is null by matching the   members lastname,firstname and dateofbirth from the file with labfiledata lastname,firstname and dateofbirth order by date in descending order .

STEP 15: Update memberid in labfiledata from DB whose memberid is null.by  joining  members memberid with the labfiledata  patientid  for  the length of patientid  is greather than 9 and the  first character should be 9  and consider first 9 characters only .

STEP 16: Update memberid in labfiledata from DB whose memberid is null. by matching   Labfiledata patientid with Labfiledata memberid

STEP 17: Update HealthPlanCode in labfiledata from DB whose HealthPlanCode is null By joining members memberid With labfiledata memberid. Where who HealthPlanCode is null and OPTHDate is null and memberid is not null   of @fileid.

STEP 18: Update HealthPlanCode in labfiledata from DB whose HealthPlanCode is null by matching lab memberid with members memberid And members OPTHDate is not null and order by opthdate in descending.

STEP 19: Update claimno in labfiledata from DB whose claimno is null by matching max claimno from claims where cpt_code ,service_date and memberid  of  claims  should match with cpt_code,service_date and memberid   of labfiledata to labfiledata  ClaimNo


STEP 20: Update claimno in labfiledata from DB whose claimno is null by matching max claimno from claims where service_date and memberid of claims should match service_date and memberid   of labfiledata to labfiledata ClaimNo whose cpt_code is null
                            
STEP 21: Updating status to completed after loading the file



           

