---
title: Coleções de esquema de OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 90899a123b3dafcd47a50ef8f6eb003938b22a03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186933"
---
# <a name="ole-db-schema-collections"></a>Coleções de esquema de OLE DB

Esta seção discute o suporte à coleta de esquemas para os provedores de OLE DB para Microsoft SQL Server, Oracle e Microsoft Jet.  
  
## <a name="microsoft-sql-server-ole-db-provider"></a>Provedor de OLE DB de Microsoft SQL Server  

 O driver de OLE DB Microsoft SQL Server dá suporte às seguintes coleções de esquema específicas, além das coleções de esquema comuns:  
  
- Tabelas  
  
- Colunas  
  
- Procedimentos  
  
- Procedimentoparameters  
  
- Catálogo  
  
- Índices  
  
### <a name="tables"></a>Tabelas  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|TABLE_TYPE|String|  
|TABLE_GUID|Guid|  
|DESCRIPTION|String|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|Datetime|  
|DATE_MODIFIED|Datetime|  
  
### <a name="columns"></a>Colunas  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|COLUMN_NAME|String|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Booliano|  
|COLUMN_DEFAULT|String|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Booliano|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|String|  
|CHARACTER_SET_SCHEMA|String|  
|CHARACTER_SET_NAME|String|  
|COLLATION_CATALOG|String|  
|COLLATION_SCHEMA|String|  
|COLLATION_NAME|String|  
|DOMAIN_CATALOG|String|  
|DOMAIN_SCHEMA|String|  
|DOMAIN_NAME|String|  
|DESCRIPTION|String|  
|COLUMN_LCID|Int32|  
|COLUMN_COMPFLAGS|Int32|  
|COLUMN_SORTID|Int32|  
|COLUMN_TDSCOLLATION|Byte[]|  
|IS_COMPUTED|Booliano|  
  
### <a name="procedures"></a>Procedimentos  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|PROCEDURE_CATALOG|String|  
|PROCEDURE_SCHEMA|String|  
|PROCEDURE_NAME|String|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|String|  
|DESCRIPTION|String|  
|DATE_CREATED|Datetime|  
|DATE_MODIFIED|Datetime|  
  
### <a name="procedureparameters"></a>Procedimentoparameters  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|PROCEDURE_CATALOG|String|  
|PROCEDURE_SCHEMA|String|  
|PROCEDURE_NAME|String|  
|PARAMETER_NAME|String|  
|ORDINAL_POSITION|Int32|  
|PARAMETER_TYPE|Int32|  
|PARAMETER_HASDEFAULT|Booliano|  
|PARAMETER_DEFAULT|String|  
|IS_NULLABLE|Booliano|  
|DATA_TYPE|Int32|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIPTION|String|  
|TYPE_NAME|String|  
|LOCAL_TYPE_NAME|String|  
  
### <a name="catalog"></a>Catálogo  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|CATALOG_NAME|String|  
|DESCRIPTION|String|  
  
### <a name="indexes"></a>Índices  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|INDEX_CATALOG|String|  
|INDEX_SCHEMA|String|  
|INDEX_NAME|String|  
|PRIMARY_KEY|Booliano|  
|UNIQUE|Booliano|  
|CLUSTERED|Booliano|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Booliano|  
|AUTO_UPDATE|Booliano|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|String|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|String|  
|INTEGRADA|Booliano|  
  
## <a name="microsoft-oracle-ole-db-provider"></a>Provedor de OLE DB Microsoft Oracle  

 O driver Microsoft Oracle OLE DB dá suporte às seguintes coleções de esquema específicas, além das coleções de esquema comuns:  
  
- Tabelas  
  
- Colunas  
  
- Procedimentos  
  
- ProcedureColumns  
  
- Procedimentoparameters  
  
- Exibições  
  
- Índices  
  
### <a name="tables"></a>Tabelas  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|TABLE_TYPE|String|  
|TABLE_GUID|Guid|  
|DESCRIPTION|String|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|Datetime|  
|DATE_MODIFIED|Datetime|  
  
### <a name="columns"></a>Colunas  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|COLUMN_NAME|String|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Booliano|  
|COLUMN_DEFAULT|String|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Booliano|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|String|  
|CHARACTER_SET_SCHEMA|String|  
|CHARACTER_SET_NAME|String|  
|COLLATION_CATALOG|String|  
|COLLATION_SCHEMA|String|  
|COLLATION_NAME|String|  
|DOMAIN_CATALOG|String|  
|DOMAIN_SCHEMA|String|  
|DOMAIN_NAME|String|  
|DESCRIPTION|String|  
  
### <a name="procedures"></a>Procedimentos  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|PROCEDURE_CATALOG|String|  
|PROCEDURE_SCHEMA|String|  
|PROCEDURE_NAME|String|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|String|  
|DESCRIPTION|String|  
|DATE_CREATED|Datetime|  
|DATE_MODIFIED|Datetime|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|PROCEDURE_CATALOG|String|  
|PROCEDURE_SCHEMA|String|  
|PROCEDURE_NAME|String|  
|COLUMN_NAME|String|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ROWSET_NUMBER|Int64|  
|ORDINAL_POSITION|Int64|  
|IS_NULLABLE|Booliano|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIPTION|String|  
|SOBRECARGA|Int16|  
  
### <a name="views"></a>Exibições  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|VIEW_DEFINITION|String|  
|CHECK_OPTION|Booliano|  
|IS_UPDATABLE|Booliano|  
|DESCRIPTION|String|  
|DATE_CREATED|Datetime|  
|DATE_MODIFIED|Datetime|  
  
### <a name="indexes"></a>Índices  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|INDEX_CATALOG|String|  
|INDEX_SCHEMA|String|  
|INDEX_NAME|String|  
|PRIMARY_KEY|Booliano|  
|UNIQUE|Booliano|  
|CLUSTERED|Booliano|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Booliano|  
|AUTO_UPDATE|Booliano|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|String|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|String|  
|INTEGRADA|Booliano|  
  
## <a name="microsoft-jet-ole-db-provider"></a>Provedor de OLE DB do Microsoft Jet  

 O driver de OLE DB do Microsoft Jet dá suporte às seguintes coleções de esquema específicas, além das coleções de esquema comuns:  
  
- Tabelas  
  
- Colunas  
  
- Procedimentos  
  
- Exibições  
  
- Índices  
  
### <a name="tables"></a>Tabelas  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|TABLE_TYPE|String|  
|TABLE_GUID|Guid|  
|DESCRIPTION|String|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|Datetime|  
|DATE_MODIFIED|Datetime|  
  
### <a name="columns"></a>Colunas  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|COLUMN_NAME|String|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Booliano|  
|COLUMN_DEFAULT|String|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Booliano|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|String|  
|CHARACTER_SET_SCHEMA|String|  
|CHARACTER_SET_NAME|String|  
|COLLATION_CATALOG|String|  
|COLLATION_SCHEMA|String|  
|COLLATION_NAME|String|  
|DOMAIN_CATALOG|String|  
|DOMAIN_SCHEMA|String|  
|DOMAIN_NAME|String|  
|DESCRIPTION|String|  
  
### <a name="procedures"></a>Procedimentos  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|PROCEDURE_CATALOG|String|  
|PROCEDURE_SCHEMA|String|  
|PROCEDURE_NAME|String|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|String|  
|DESCRIPTION|String|  
|DATE_CREATED|Datetime|  
|DATE_MODIFIED|Datetime|  
  
### <a name="views"></a>Exibições  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|VIEW_DEFINITION|String|  
|CHECK_OPTION|Booliano|  
|IS_UPDATABLE|Booliano|  
|DESCRIPTION|String|  
|DATE_CREATED|Datetime|  
|DATE_MODIFIED|Datetime|  
  
### <a name="indexes"></a>Índices  
  
|ColumnName|Tipo de dados|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|INDEX_CATALOG|String|  
|INDEX_SCHEMA|String|  
|INDEX_NAME|String|  
|PRIMARY_KEY|Booliano|  
|UNIQUE|Booliano|  
|CLUSTERED|Booliano|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Booliano|  
|AUTO_UPDATE|Booliano|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|String|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|String|  
|INTEGRADA|Booliano|  
  
## <a name="see-also"></a>Veja também

- [Visão geral do ADO.NET](ado-net-overview.md)
