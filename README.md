# Log Parser - ODBC - SCCM Defender AV logs

SCCM/SCEP no longer writes the AV logs to the event log on the SCCM server.  You need to query the SQL DB

* Deploy the typespec to the log collector service
* /etc/netwitness/ng/logcollection/content/collection/odbc/
* Deploy the parser to the log decoder and enable

You can upload the .envision file to the log decoder using the parser tab in >config and upload.

You will have to update the SQL in the typespec file for your SCCM instance as a view is used and that name changes with each instance installed

FROM [CM_CA1].[dbo].[v_AM_NormalizedDetectionHistory]

CM_CA1 - update on your SCCM instance
