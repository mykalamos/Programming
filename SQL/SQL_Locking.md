Lock granularity
----------------

Rogue           Row             (RID)
King            Key             (KEY)
Proposes        Page            (PAG)
Equal           Extent          (EXT)
Tax             Table           (TAB)
Dodge           Database        (DB)

Use sp_lock in transaction

RID
===
- Single Row on a table on update/delete.

sp_lock output For single row delete

spid    dbid    ObjId   IndId   Type    Resource        Mode    Status
----------------------------------------------------------------------
61      13      0       0       DB                      S       GRANT
61      13      123     0       PAG     1:242           IX      GRANT
61      13      123     0       RID     1:242:0         X       GRANT
61      13      123     0       TAB                     IX      GRANT

Resource locked represented by: DatabaseID:FileID:PageID:Slot(row)

DatabaseID = dbid
FileID     = Resource[0]
PageID     = Resource[1]
Slot(Row)  = Resource[2]

Table:  SELECT OBJECT_NAME(123)
DB:     SELECT DB_NAME(13)

Concurrency: High - only a single affected by blocking.

KEY
===
- Row lock within an index.
- For clustered indexes only a KEY lock is acquired.

sp_lock output For single row delete:

spid    dbid    ObjId   IndId   Type    Resource        Mode    Status
----------------------------------------------------------------------
61      13      0       0       DB                      S       GRANT
61      13      124     1       PAG     1:244           IX      GRANT
61      13      124     0       TAB                     IX      GRANT
61      13      124     1       KEY     (0100)          X       GRANT

Resource locked represented by: DatabaseID:ObjectID:IndexID(Hash value for index key)

Represented as 13:124:1 (01005221bd04) - where 1 is the IndId.

Concurrency: High - only a single affected by blocking.

PAG
===
- Lock Manager determines resource pressure of multiple KEY/RID locks and may take out a page lock instead.
- DatabaseID:FileID:PageID
- Improves individual query perf but hurts conncurrency.

EXT
===
- Extent is 8 contiguous data/index pages.
- Used e.g. during DBCC DBREINDEX while pages may be moved from one extent to another.

TAB
===
- Reserves access to a table and its indexes.
- DatabaseID:ObjectID
- Least overhead but hurts concurrency.

DB
==
- 
