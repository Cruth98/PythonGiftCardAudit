# PythonGiftCardAudit
This hub is to store the code and notebooks used for Ad-Hoc audit requests resolved using Python.

# Inside this REPO you should find 3 major audit requests that were resolved on short notice:
1) INCOMM Running Sum
2) Givex Trans List
3) BHN Running Sum

_** Additional Detail -- **_
1) **The INCOMM_RunningSum File** is the first audit request given. 
Head of the Gift Card Accounting Team was unable to tie out the data, given it was such a large file (>5GB). Additionally, the process needed to be iterative, such that it calculated the running subtotal at each record level. The file was too large to be loaded into excel, so I was asked to calculate the data and send back aggregated to the Gift Card team.

2) **The Givex Trans List** file was a request from Treasury. They had an immediate request from their audit team and the CFO, to which they were unable to figure out without assistance. The file again was too large to parse through in Excel. I was required to group the large data by processor type and date. The Processor type needed slight conversion, but the end result was simply just aggregating by the necessary columns and returning in a readable .csv format to the Treasury department.

3) **The BHN Running Sum** was the exact same request as the INCOMM Running Sum, except this time for a separate vendor. They saw how well the first method worked and wanted to replicate that on a new vendor. This is now the new and accepted process by our audit department. 
