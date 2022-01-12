Cursor syntax
-------------

1. DECLARE <Cursor_Name> CURSOR [Options] FOR <Select Statement>
2. OPEN <Cursor_name>
3. FETCH <Cursor_name>
4. CLOSE <Cursor_Name>
5. DEALLOCATE <Cursor_Name>

DOFCD

Cursor types
------------
Static - data copied into tempdb.
Keyset - Default, pk data copied into tempdb. New rows can't be seen. For
deleted rows nulls are returned with @@FETCH_STATUS or -2. More time to open
than dynamic but use fewer resources.
Dynamic - like Keyset but can see new rows. Key data is refreshed on base
table modification and order is not preserved. Most expensive.
Fast_Forward - optimal only supports FETCH NEXT

These options control:
Scope - local, global
Scrollability - next row only, direction
Membership
Updatablity - not static, primary key on base tables, where clause
