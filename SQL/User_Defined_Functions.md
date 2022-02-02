# User Defined Functions
https://docs.microsoft.com/en-us/sql/relational-databases/user-defined-functions/user-defined-functions?view=sql-server-ver15

Routines that
- Accept parameters
- Perform an action
- Return a scalar value or result set

## Benefits
- Allow modular programming - shared functionality
- Faster execution - caching and reusing plans
- Reduce network traffic

## Types
- Scalar - single value ``` RETURNS ```
- Table Valued - result set ``` SELECT ... ```
- System

## Valid actions
- Operations local to function
- Not ```TRY ... CATCH```
