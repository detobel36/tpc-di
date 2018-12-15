# Data Warehouse - TPC-DI

## Installation

### Tools

This project have be done with Visual Studio 2017 and a Microsoft SQL Database.


### Installation

- First download the TPC-DI tool and generate data.     
- Save the generated data in the following folder: `C:\Users\Public\Documents\TPC-DI\Batch1` (see "Configuration" point for more informations).      
- Copy also the file `CustomerMgmt.xsd` (in the same folder).        
- Create a database `destination_di` on your local database and execute the file `createTables.sql`.     


### Configuration

- **Database**     
  This project work with Microsoft SQL Database.  This database is in localhost (use hostname `.`).     
- **Files**         
  All the files are store at the same place (which not user dependant).  Indeed, we choose a "public" folder: `C:\Users\Public\Documents\TPC-DI\Batch1`


## Files

- [`CustomerMgmt.xsd`](CustomerMgmt.xsd)       
  Used by DimCustomer.dtsx to open XML file
- [`DimCompany.dtsx`](DimCompany.dtsx)       
  ETL for DimCompany, DimSecurity and Financial (they use FINWIRE files)
- [`DimCustomer.dtsx`](DimCustomer.dtsx)       
  ETL for DimCustomer
- [`FactMarketHistory.dtsx`](FactMarketHistory.dtsx)    
  ETL for FactMarketHistory (use DailyMarket.txt)     
  :warning: Not yet finish  
- [`ReferenceTable+DimBroker.dtsx`](ReferenceTable+DimBroker.dtsx)       
  ETL for ReferenceTable (DimDate, DimTime, TradeType, StatusType, TaxRate, Industry) but also DimBroker
- [`createTables.sql`](createTables.sql)       
  Create destination database