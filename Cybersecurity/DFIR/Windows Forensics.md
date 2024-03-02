## Master File Table(MFT)
- Contained in the **NTFS**
- It contains all information about files in the file system, including itself; information like size, time, permissions, data content and date stamps
- It also stores the metadata even if the file itself has been deleted.
- if the the size of a particular file is lower than 1KB then it will be stored in the MFT itself, these are called **MFT resident files**
- **MFTCmd** and **MFTExplorere** are good tools for this
- 