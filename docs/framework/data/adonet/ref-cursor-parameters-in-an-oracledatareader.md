---
title: Parâmetros de REF CURSOR em um OracleDataReader
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 801dff0f-2508-45aa-9416-f45d6887740c
ms.openlocfilehash: 0b9ded8c29dfa7d94b6f9b121a1004f2ad9ad6e0
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739497"
---
# <a name="ref-cursor-parameters-in-an-oracledatareader"></a>Parâmetros de REF CURSOR em um OracleDataReader

Este exemplo de Visual Basic da Microsoft executa um procedimento armazenado PL/SQL que retorna um parâmetro de CURSOR REF e lê o valor como um <xref:System.Data.OracleClient.OracleDataReader> .

```vb
Private Sub Button1_Click(ByVal sender As Object, _
  ByVal e As System.EventArgs) Handles Button1.Click

  Dim connString As New String(_
      "Data Source=Oracle9i;User ID=scott;Password=[PLACEHOLDER];")
  Using conn As New OracleConnection(connString)
    Dim cmd As New OracleCommand()
    Dim rdr As OracleDataReader

    conn.Open()
    cmd.Connection = conn
    cmd.CommandText = "CURSPKG.OPEN_ONE_CURSOR"
    cmd.CommandType = CommandType.StoredProcedure
    cmd.Parameters.Add(New OracleParameter(
      "N_EMPNO", OracleType.Number)).Value = 7369
    cmd.Parameters.Add(New OracleParameter(
      "IO_CURSOR", OracleType.Cursor)).Direction = ParameterDirection.Output

    rdr = cmd.ExecuteReader()
    While (rdr.Read())
        REM do something with the values
    End While

    rdr.Close()
  End Using
End Sub
```

## <a name="see-also"></a>Confira também

- [REF CURSORs do Oracle](oracle-ref-cursors.md)
- [Visão geral do ADO.NET](ado-net-overview.md)
