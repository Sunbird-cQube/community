### Steps for Mock Data Processing
Create the directory and place the data files as shown in file structure below inside the emission directory.

##### Scripts:
Scripts folder contains the Python code to generate the mockup data and the data configrations.

##### test_data_lite:
test_data_lite folder contains the data with a sample of few records(3 schools) to make the cQube light weight. This data will be used just for the lighter demos. 

##### test_data:
test_data folder contains the data with one million of records to describe a perfect view of cQube demo.
<br></br>
<br></br>

**Based on the requirement the data can be selected from either test_data_lite/test_data**

**Note : Process the data files one after the another.**
##### Master Files
- district_master
    - district_mst.zip
        - district_mst.csv
 - block_master
    - block_mst.zip
        - block_mst.csv
- cluster_master
    - cluster_mst.zip
        - cluster_mst.csv
- school_master
    - school_mst.zip
        - school_mst.csv
- school_management
    - school_management_master.zip
        - school_management_master.csv
- diksha_enrolment
    - diksha_enrolment_tpd.zip
        - diksha_enrolment_tpd.csv

##### Transactional Files

**Student Attendance Data Processing**
- student_attendance
    - student_attendance.zip
        - student_attendance.csv

**Teacher Attendance Data Processing**
- teacher_attendance
    - teacher_attendance.zip
        - teacher_attendance.csv

**Infrastructure Data Processing**
- infra_trans
    - infra_trans.zip
        - infra_trans.csv

**CRC Data Processing**
- inspection_master
    - inspection_master.zip
        - inspection_master.csv
- user_location_master
    - user_location_master.zip
        - user_location_master.csv

**SAT Data Processing**
- sat
    - semester_exam_grade_details.zip
        - semester_exam_grade_details.csv
    - semester_exam_subject_details.zip
        - semester_exam_subject_details.csv
    - semester_exam_mst.zip
        - semester_exam_mst.csv
    - semester_exam_qst_mst.zip
        - semester_exam_qst_mst.csv
    - semester_exam_result_trans.zip
        - semester_exam_result_trans.csv
