# Data Warehouse - TPC-DI

### Tools and Instalation
This project have be done with Visual Studio.  Data are extract from the TPC-DI files and store to a datbase.       
So first of all, you need to generate data with TPC-DI tools.  Saved all files in the folder `C:\Users\Public\Documents\TPC-DI\Batch1` (see "Configuration" point for more informations).
You also need to add the file `CustomerMgmt.xsd` (in the same folder).        
Finally, you need to execute the file `createTables.sql` on your local database: `destination_di`


### Configuration

- **Database**     
  This project work with Microsoft SQL Database.  This database is in localhost (use hostname `.`).     
- **Files**         
  All the files are store at the same place (which not user dependant).  Indeed, we choose a "public" folder: `C:\Users\Public\Documents\TPC-DI\Batch1`

