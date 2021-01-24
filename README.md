# SQLiteLibrary_framework
Project for working with SQLite databases

Dependence .NET Framework >= 4.6.2

Built-in CRUD functions provide convenient and fast work with any SQLite databases
There are also functions to find a specific field in a table, create and delete entire tables

# How to use ?

1 - You need to connect the library via nuget using the link https://www.nuget.org/packages/SQLiteLibrary/

2 - Create database file. Can be used DB Browser software https://sqlitebrowser.org/

3 - In the project you need to add the App.config file, if it is not there, and add the following lines to it

<connectionStrings>
    
    <add name="$StringID$" connectionString="Data Source=.\DBFileName.db;Version=3" providerName="System.Data.SqlClient" />
    
</connectionStrings>

4 - You need to create an object through which you can interact with the database


SQLite<Model> sqlitedb = new SQLite<Model>("$StringID$", "$TableName$");

The first parameter accepts an identifier declared in the App.config file to connect to a specific database file

Second - is the table name

# Syntax

# namespace SQLiteLibrary

Add new note to db:

sqlitedb.Add(model));


Add new note or update exists:


sqlitedb.AddOrUpdate(model);


Clear all table from notes:


sqlitedb.Clear(tablename); // Cleare selected table

sqlitedb.Clear(); // Cleare current table

Create a new table:

sqlitedb.Create(tablename);

Delete tabel:

sqlitedb.Delete(tablename); // Delete selected table

sqlitedb.Delete(); // Delete current table

Load all notes from current table:

sqlitedb.Load();

Remove note from table:

sqlitedb.Remove(model); // Remove selected note from table. The default search is by ID

sqlitedb.Remove(model, x => x.Login); // Remove selected note from table. Search is performed by the specified property (In the example, by the value of the field Login)


Search note:

sqlitedb.Search(model); // The default search is by ID

sqlitedb.Search(model, x => x.Login); // Search is by selected property - Login

Update exists note:

sqlitedb.Update(model); // Upadate is be from default ID property

sqlitedb.Update(model, x => x.login); // Upadate is be from selected property - Login


# Important!

If, after building the project, the x86 x64 folders did not appear in the DEBUG folder, then they need to be added to the manual
