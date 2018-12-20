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
- [`DimAccount.dtsx`](DimAccount.dtsx)          
  ELT for DimAccount (use CustomerMgmt.xml (and thus CustomerMgmt.xsd))
- [`DimCompany.dtsx`](DimCompany.dtsx)       
  ETL for DimCompany, DimSecurity and Financial (they use FINWIRE files)
- [`DimCustomer.dtsx`](DimCustomer.dtsx)       
  ETL for DimCustomer    
  **TODO:** missing Phone, NationalTaxRateDesc, LocalTaxRateDesc...
- [`DimTrade.dtsx`](DimTrade.dtsx)    
  ETL for DimTrade (use TradeHistory.txt and Trade.txt)
- [`FactCashBalance.dtsx`](FactCashBalance.dtsx)     
  ETL for FactCashBalance (use CashTransaction.txt)    
- [`FactHoldings.dtsx`](FactHoldings.dtsx)    
  ETL for FactHoldings (use HoldingHistory.txt and DimTrade)
- [`FactMarketHistory.dtsx`](FactMarketHistory.dtsx)    
  ETL for FactMarketHistory (use DailyMarket.txt)      
- [`FactWatches.dtsx`](FactWatches.dtsx)   
  ETL for FactWatches (use WatchHistory.txt)
- [`Prospect.dtsx`](Prospect.dtsx)    
  ETL for Prospect (use ?)         
  **TODO:** Not finish, need to debug
- [`ReferenceTable+DimBroker.dtsx`](ReferenceTable+DimBroker.dtsx)       
  ETL for ReferenceTable (DimDate, DimTime, TradeType, StatusType, TaxRate, Industry) but also DimBroker
- [`createTables.sql`](createTables.sql)       
  Create destination database