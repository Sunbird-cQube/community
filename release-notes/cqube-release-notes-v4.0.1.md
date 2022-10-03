# cQube - Release V 4.0-aplha( Work In Progress )


#### Document Release Version

|Project    |Release Date    |Release Version|
|---------|----------------|------------------|
|cQube    | Oct 2022 |V 4.0-aplha    |


## cQube-v4.0.1 Release Notes
https://docs.google.com/document/d/1hvBSQFhZ5C2h4NtMkRqoTxQ2Joa4cSSkdIhRpjw9vu8/edit?usp=sharing

## Installation 

[Installation steps](https://github.com/Sunbird-cQube/cQube_Edu/tree/cqube-v4.0.1)


## Known Issues
This release has certain known issues. Given below is a summary of these issues along with any applicable workarounds.

### Admin UI
- Admin UI is available without VPN support and only for S3.
- Workaround - None

### Automatic Upgrade
- Automatic upgrade is unavailable.
- Workaround - Users may upgrade the application manually by following these steps:

  - Migrate database from existing cQube installation to v4.0.1 installation. Instructions: <ATTACH ayesha DOC>.
  - Create KeyCloak users for the upgraded installation. Instructions: <ATTACH sharath DOC>.

### Visualization
- Visualization is supported only for S3.
- Workaround - None

### Telemetry
- Telemetry is not included.
- Workaround - None

### PAT File Processing
- PAT file processing may get halted during processing.
- Workaround - Field Support will need to run a script manually to resume the processing. 
  #### Follow the below link for Instructions: 
  https://docs.google.com/document/d/1uWmL5Ihmbt_2RzJGx1uYSG66T-M1JPtzAs45JI8qWRc/edit?usp=sharing

### Map Legends
- Map legends for Textbook Distribution are supported when the number of markers is more than 10 (for all other reports legends are supported for any number of markers).
- Workaround - None




