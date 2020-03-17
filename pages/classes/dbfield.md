---
layout: page
title: "DbField (RepoDb)"
permalink: /class/dbfield
tags: [repodb, class, dbfield, orm, hybrid-orm, sqlserver, sqlite, mysql, postgresql]
---

## DbField

This is the class that holds the definition of the database columns. This class is mutable. The library is using the [IDbHelper](/interface/idbhelper) method named `GetFields()` to extract the database columns.

```csharp
using (var connection = new SqlConnection(connectionString))
{
    var helper = connection.GetDbHelper();
    var dbFields = helper.GetFields(connection, "[dbo].[Person]");
    // Do the stuffs for the 'dbFields' here
}
```

#### List of Properties

- **Name** - the name of the column.
- **IsPrimary** - `True` if the column is primary.
- **IsIdentity** - `True` if the column is identity.
- **IsNullable** - `True` if the column is nullable.
- **Type** - the equivalent .NET CLR type.
- **Size** - the size of the column from the database.
- **Precision** - the precision of the column from the database.
- **Scale** - the scale of the column from the database.
- **DatabaseType** - tye type of the column from the database.

> We suggest that you should limit the use of this class in any of your development, unless very necessary. 