<div align="center">

## ado\.net


</div>

### Description

Gives a basic knowldge of ADO.NET
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[m\.shihipar](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/m-shihipar.md)
**Level**          |Beginner
**User Rating**    |3.8 (15 globes from 4 users)
**Compatibility**  |VB\.NET
**Category**       |[Databases](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/databases__10-5.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/m-shihipar-ado-net__10-1083/archive/master.zip)





### Source Code

```
Option Strict Off
Option Explicit On
Imports System
Imports System.Data.OleDb
 sub whatever()
 Dim myconnection As New OleDbConnection()
 Dim myReader As OleDbDataReader
 Dim cmSQL As OleDbCommand
 Dim strSQL As String
 myconnection.ConnectionString = "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=C:\ database.mdb;"
 ('or add the database in bin folder of the project and substitute with the following)
myconnection.ConnectionString = "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=database.mdb;"
 Try
  strSQL = "SELECT * FROM tablename"
  cmSQL = New OleDbCommand(strSQL, myconnection)
  myconnection.Open()
  myReader = cmSQL.ExecuteReader()
  Do While myReader.Read()
  Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", myReader.GetInt32(0), myReader.GetString(1))
  Loop
 Catch Exp As OleDbException
  MsgBox(Exp.Message, MsgBoxStyle.Critical, "Oledb Error")
 Catch Exp As Exception
  MsgBox(Exp.Message, MsgBoxStyle.Critical, "General Error")
 End Try
 ' Close and Clean up objects
 myconnection.Close()
 cmSQL.Dispose()
 myconnection.Dispose()
 myReader.Close)
 end sub
```

