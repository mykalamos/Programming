# Stored Procedures
https://docs.microsoft.com/en-us/sql/relational-databases/stored-procedures/stored-procedures-database-engine?view=sql-server-ver15
- Group of one or more sql statements
- CLR function
- Accepts inputs and output parameters
- Call other database objects
- Return status

# Benefits
- Reduced network traffic - encapsulation of multiple operations
- Security - Permissioning to a procedure but no underlying objects ``` GRANT ```
  - ``` EXECUTE AS ```
  - Implementation hidden
- Can be encrypted - obfuscation
- Code reuse
- Separation of concerns - maintenance
- Performance
  - Compiles on first execution - query plan reused subsequently
  - Recompilation may be required following changes to underlying objects

## Types
- User Defined
- Temporary
  - Stored in TempDb
  - Local/Global (#/##)
    - Global = any user
- System
 - Included with Engine
- Extended User Defined
  - Creating procedures as dlls in e.g. C
  - Being removed in future version -> CLR instead

```
CREATE PROCEDURE dbo.uspGetData
    @LastName varchar(50),   
    @FirstName varchar(50)   
AS   

    SET NOCOUNT ON;  
    SELECT col1, col2 from dbo.MyTable t
    WHERE t.LastName = @LastName and t.FirstName = @FirstName;
GO
```
