---
title: SchemaEnum (Access Desktop Database Reference)
TOCTitle: SchemaEnum
ms:assetid: 6147b682-3c4f-ea91-fff6-ac73107d206d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249359(v=office.15)
ms:contentKeyID: 48545208
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: aa70f275de164716b5b3975b56588e9dc4aec1a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308863"
---
# <a name="schemaenum"></a>SchemaEnum

**Gilt für**: Access 2013, Office 2013

Der Typ des **Recordset** -Schemaobjekts wird angegeben, das von der [OpenSchema](openschema-method-ado.md)-Methode abgerufen wird.

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu der Funktion und den Spalten, die für jede ADO-Konstante zurückgegeben werden, finden Sie in den Themen von Anhang B der *OLE DB Programmer's Reference*. Die Namen der einzelnen Themen werden in Klammern im Abschnitt Description der folgenden Tabelle aufgeführt.

Weitere Informationen zu der Funktion und den Spalten, die für jede ADO MD-Konstante zurückgegeben werden, finden Sie in Kapitel 23 der Dokumentation zu *OLE DB für OLAP*. Die Namen der einzelnen Themen werden in Klammern aufgelistet und mit einem Sternchen (\*) in der Spalte Description der folgenden Tabelle gekennzeichnet.

Translate the data types of columns in the OLE DB documentation to ADO data types by referring to the Description column of the ADO [DataTypeEnum](datatypeenum.md) topic. Ein OLE DB-Datentyp von **\_DbType WSTR** entspricht beispielsweise einem ADO-Datentyp von **adWChar**.

ADO generates schema-like results for the constants, **adSchemaDBInfoKeywords** and **adSchemaDBInfoLiterals**. ADO erstellt ein **Recordset**-Objekt und füllt dann jede Zeile mit den Werten, die von den **IDBInfo:: GetKeywords** -und **IDBInfo:: GetLiteralInfo** -Methoden zurückgegeben werden. Weitere Informationen zu diesen Methoden finden Sie im Abschnitt IDBInfo der *OLE DB Programmer es Reference*.

<br/>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Konstante</p></th>
<th><p>Wert</p></th>
<th><p>Beschreibung</p></th>
<th><p>Einschränkungsspalten</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adSchemaAsserts</strong></p></td>
<td><p>0</p></td>
<td><p>Gibt die im Katalog definierten Assertionen zurück, die einem bestimmten Benutzer gehören. (ASSERTIONS-Rowset)</p></td>
<td><p>CONSTRAINT_CATALOG<br />
CONSTRAINT_SCHEMA<br />
CONSTRAINT_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaCatalogs</strong></p></td>
<td><p>1</p></td>
<td><p>Gibt die physikalischen Attribute zurück, die Katalogen zugeordnet sind, auf die vom DBMS zugegriffen werden kann. (CATALOGS-Rowset)</p></td>
<td><p>CATALOG_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaCharacterSets</strong></p></td>
<td><p>2</p></td>
<td><p>Gibt die im Katalog definierten Zeichensätze zurück, auf die ein bestimmter Benutzer zugreifen kann. (CHARACTER_SETS-Rowset)</p></td>
<td><p>CHARACTER_SET_CATALOG<br />
CHARACTER_SET_SCHEMA<br />
CHARACTER_SET_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaCheckConstraints</strong></p></td>
<td><p>5</p></td>
<td><p>Gibt die im Katalog definierten CHECK-Einschränkungen zurück, die einem bestimmten Benutzer gehören. (CHECK_CONSTRAINTS-Rowset)</p></td>
<td><p>CONSTRAINT_CATALOG<br />
CONSTRAINT_SCHEMA<br />
CONSTRAINT_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaCollations</strong></p></td>
<td><p>3</p></td>
<td><p>Gibt die im Katalog definierten Sortierungen zurück, auf die ein bestimmter Benutzer zugreifen kann. (COLLATIONS-Rowset)</p></td>
<td><p>COLLATION_CATALOG<br />
COLLATION_SCHEMA<br />
COLLATION_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaColumnPrivileges</strong></p></td>
<td><p>13</p></td>
<td><p>Gibt die im Katalog definierten Tabellenspaltenberechtigungen zurück, die einem bestimmten Benutzer zur Verfügung stehen oder von diesem erteilt werden. (COLUMN_PRIVILEGES-Rowset)</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME<br />
COLUMN_NAME<br />
RECHTEFÜR<br />
GRANTEE</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaColumns</strong></p></td>
<td><p>4</p></td>
<td><p>Gibt die im Katalog definierten Tabellenspalten (einschließlich Sichten) zurück, auf die ein bestimmter Benutzer zugreifen kann. (COLUMNS-Rowset)</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME<br />
COLUMN_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaColumnsDomainUsage</strong></p></td>
<td><p>11</p></td>
<td><p>Gibt die im Katalog definierten Spalten zurück, die von einer im Katalog definierten Domäne abhängig sind und einem bestimmten Benutzer gehören. (COLUMN_DOMAIN_USAGE-Rowset)</p></td>
<td><p>DOMAIN_CATALOG<br />
DOMAIN_SCHEMA<br />
DOMAIN_NAME<br />
COLUMN_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaConstraintColumnUsage</strong></p></td>
<td><p>6</p></td>
<td><p>Gibt die im Katalog definierten Spalten zurück, die von referenziellen Einschränkungen, eindeutigen Einschränkungen, CHECK-Einschränkungen und Assertionen verwendet werden und einem bestimmten Benutzer gehören. (CONSTRAINT_COLUMN_USAGE-Rowset)</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME<br />
COLUMN_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaConstraintTableUsage</strong></p></td>
<td><p>7</p></td>
<td><p>Gibt die im Katalog definierten Tabellen zurück, die von referenziellen Einschränkungen, eindeutigen Einschränkungen, CHECK-Einschränkungen und Assertionen verwendet werden und einem bestimmten Benutzer gehören. (CONSTRAINT_TABLE_USAGE-Rowset)</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaCubes</strong></p></td>
<td><p>32</p></td>
<td><p>Gibt Informationen zu den verfügbaren Cubes in einem Schema zurück (oder im Katalog, wenn der Anbieter keine Schemas unterstützt). (CUBES-Rowset*)</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
CUBE_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaDBInfoKeywords</strong></p></td>
<td><p>30</p></td>
<td><p>Gibt eine Liste anbieterspezifischer Schlüsselwörter zurück. (IDBInfo:: getKeywords *)</p></td>
<td><p>&lt;Keine&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaDBInfoLiterals</strong></p></td>
<td><p>31</p></td>
<td><p>Gibt eine Liste anbieterspezifischer Literale zurück, die in Textbefehlen verwendet werden. (IDBInfo:: GetLiteralInfo *)</p></td>
<td><p>&lt;Keine&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaDimensions</strong></p></td>
<td><p>33</p></td>
<td><p>Gibt Informationen zu den Dimensionen in einem bestimmten Cube zurück. Es verfügt über eine Zeile für jede Dimension. (DIMENSIONS-Rowset *)</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
CUBE_NAME<br />
DIMENSION_NAME<br />
DIMENSION_UNIQUE_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaForeignKeys</strong></p></td>
<td><p>27</p></td>
<td><p>Gibt die Fremdschlüsselspalten zurück, die im Katalog von einem bestimmten Benutzer definiert wurden. (FOREIGN_KEYS-Rowset)</p></td>
<td><p>PK_TABLE_CATALOG<br />
PK_TABLE_SCHEMA<br />
PK_TABLE_NAME<br />
FK_TABLE_CATALOG<br />
FK_TABLE_SCHEMA<br />
FK_TABLE_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaHierarchies</strong></p></td>
<td><p>34</p></td>
<td><p>Gibt Informationen zu den in einer Dimension unterstützten Hierarchien zurück. (HIERARCHIES-Rowset *)</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
CUBE_NAME<br />
DIMENSION_UNIQUE_NAME<br />
HIERARCHY_NAME<br />
HIERARCHY_UNIQUE_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaIndexes</strong></p></td>
<td><p>12</p></td>
<td><p>Gibt die im Katalog definierten Indizes zurück, die einem bestimmten Benutzer gehören. (INDEXES-Rowset)</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
INDEX_NAME<br />
Typ<br />
TABLE_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaKeyColumnUsage</strong></p></td>
<td><p>8</p></td>
<td><p>Gibt die im Katalog definierten Spalten zurück, die von einem bestimmten Benutzer als Schlüssel eingeschränkt werden. (KEY_COLUMN_USAGE-Rowset)</p></td>
<td><p>CONSTRAINT_CATALOG<br />
CONSTRAINT_SCHEMA<br />
CONSTRAINT_NAME<br />
TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME<br />
COLUMN_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaLevels</strong></p></td>
<td><p>35</p></td>
<td><p>Gibt Informationen zu den in einer Dimension verfügbaren Ebenen zurück. (LEVELS-Rowset*)</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
CUBE_NAME<br />
DIMENSION_UNIQUE_NAME<br />
HIERARCHY_UNIQUE_NAME<br />
LEVEL_NAME<br />
LEVEL_UNIQUE_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaMeasures</strong></p></td>
<td><p>36</p></td>
<td><p>Gibt Informationen zu den verfügbaren Measures zurück. (MEASURES-Rowset *)</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
CUBE_NAME<br />
MESSGRÖßE<br />
MEASURE_UNIQUE_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaMembers</strong></p></td>
<td><p>38</p></td>
<td><p>Gibt Informationen zu den verfügbaren Elementen zurück. (MEMBERS-Rowset *)</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
CUBE_NAME<br />
DIMENSION_UNIQUE_NAME<br />
HIERARCHY_UNIQUE_NAME<br />
LEVEL_UNIQUE_NAME<br />
LEVEL_NUMBER<br />
MEMBER_NAME<br />
MEMBER_UNIQUE_NAME<br />
MEMBER_CAPTION<br />
MEMBER_TYPE<br />
Tree-Operator (Weitere Informationen finden Sie in der Dokumentation zu OLE DB für OLAP.)</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaPrimaryKeys</strong></p></td>
<td><p>28</p></td>
<td><p>Gibt die Primärschlüsselspalten zurück, die im Katalog von einem bestimmten Benutzer definiert wurden. (PRIMARY_KEYS-Rowset)</p></td>
<td><p>PK_TABLE_CATALOG<br />
PK_TABLE_SCHEMA<br />
PK_TABLE_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaProcedureColumns</strong></p></td>
<td><p>29</p></td>
<td><p>Gibt Informationen zu den Spalten von Rowsets zurück, die von Prozeduren zurückgegeben werden. (PROCEDURE_COLUMNS-Rowset)</p></td>
<td><p>PROCEDURE_CATALOG<br />
PROCEDURE_SCHEMA<br />
PROCEDURE_NAME<br />
COLUMN_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaProcedureParameters</strong></p></td>
<td><p>26</p></td>
<td><p>Gibt Informationen zu den Parametern und Rückgabecodes der Prozeduren zurück. (PROCEDURE_PARAMETERS-Rowset)</p></td>
<td><p>PROCEDURE_CATALOG<br />
PROCEDURE_SCHEMA<br />
PROCEDURE_NAME<br />
PARAMETER_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaProcedures</strong></p></td>
<td><p>16</p></td>
<td><p>Gibt die im Katalog definierten Prozeduren zurück, die einem bestimmten Benutzer gehören. (PROCEDURES-Rowset)</p></td>
<td><p>PROCEDURE_CATALOG<br />
PROCEDURE_SCHEMA<br />
PROCEDURE_NAME<br />
PROCEDURE_TYPE</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaProperties</strong></p></td>
<td><p>37</p></td>
<td><p>Gibt Informationen zu den verfügbaren Eigenschaften für jede Ebene der Dimension zurück. (PROPERTIES-Rowset *)</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
CUBE_NAME<br />
DIMENSION_UNIQUE_NAME<br />
HIERARCHY_UNIQUE_NAME<br />
LEVEL_UNIQUE_NAME<br />
MEMBER_UNIQUE_NAME<br />
PROPERTY_TYPE<br />
PROPERTY_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaProviderSpecific</strong></p></td>
<td><p>-1</p></td>
<td><p>Wird verwendet, wenn der Anbieter eigene, nicht standardmäßige Schemaabfragen definiert.</p></td>
<td><p>&lt;Anbieter spezifisch&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaProviderTypes</strong></p></td>
<td><p>22</p></td>
<td><p>Gibt die (Basis-)Datentypen zurück, die vom Datenprovider unterstützt werden. (PROVIDER_TYPES-Rowset)</p></td>
<td><p>DATA_TYPE<br />
BEST_MATCH</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdSchemaReferentialConstraints</strong></p></td>
<td><p>9</p></td>
<td><p>Gibt die im Katalog definierten referenziellen Einschränkungen zurück, die einem bestimmten Benutzer gehören. (REFERENTIAL_CONSTRAINTS-Rowset)</p></td>
<td><p>CONSTRAINT_CATALOG<br />
CONSTRAINT_SCHEMA<br />
CONSTRAINT_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaSchemata</strong></p></td>
<td><p>17</p></td>
<td><p>Gibt die Schemas (Datenbankobjekte) zurück, die einem bestimmten Benutzer gehören. (SCHEMATA-Rowset)</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
SCHEMA_OWNER</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaSQLLanguages</strong></p></td>
<td><p>18</p></td>
<td><p>Gibt die Konformitätsebenen, die Optionen und die Dialekte zurück, die von den Verarbeitungsdaten der SQL-Implementierung unterstützt werden. (SQL_LANGUAGES-Rowset)</p></td>
<td><p>&lt;Keine&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaStatistics</strong></p></td>
<td><p>19</p></td>
<td><p>Gibt die im Katalog definierten Statistiken zurück, die einem bestimmten Benutzer gehören. (STATISTICS-Rowset)</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaTableConstraints</strong></p></td>
<td><p>10</p></td>
<td><p>Gibt die im Katalog definierten Tabelleneinschränkungen zurück, die einem bestimmten Benutzer gehören. (TABLE_CONSTRAINTS-Rowset)</p></td>
<td><p>CONSTRAINT_CATALOG<br />
CONSTRAINT_SCHEMA<br />
CONSTRAINT_NAME<br />
TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME<br />
CONSTRAINT_TYPE</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaTablePrivileges</strong></p></td>
<td><p>14</p></td>
<td><p>Gibt die im Katalog definierten Tabellenberechtigungen zurück, die einem bestimmten Benutzer zur Verfügung stehen oder von diesem erteilt werden. (TABLE_PRIVILEGES-Rowset)</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME<br />
RECHTEFÜR<br />
GRANTEE</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaTables</strong></p></td>
<td><p>20</p></td>
<td><p>Gibt die im Katalog definierten Tabellen (einschließlich Sichten) zurück, auf die ein bestimmter Benutzer zugreifen kann. (TABLES-Rowset)</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME<br />
_TYPE</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaTranslations</strong></p></td>
<td><p>21</p></td>
<td><p>Gibt die im Katalog definierten Zeichenumwandlungen zurück, auf die ein bestimmter Benutzer zugreifen kann. (TRANSLATIONS-Rowset)</p></td>
<td><p>TRANSLATION_CATALOG<br />
TRANSLATION_SCHEMA<br />
TRANSLATION_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaTrustees</strong></p></td>
<td><p>39</p></td>
<td><p>Reserviert für eine zukünftige Verwendung.</p></td>
<td><p><br />
</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaUsagePrivileges</strong></p></td>
<td><p>15</p></td>
<td><p>Gibt die im Katalog definierten USAGE-Berechtigungen zurück, die einem bestimmten Benutzer zur Verfügung stehen oder von diesem erteilt werden. (USAGE_PRIVILEGES-Rowset)</p></td>
<td><p>OBJECT_CATALOG<br />
OBJECT_SCHEMA<br />
OBJECT_NAME<br />
OBJECT_TYPE<br />
RECHTEFÜR<br />
GRANTEE</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaViewColumnUsage</strong></p></td>
<td><p>24</p></td>
<td><p>Gibt die Spalten zurück, von denen die angezeigten Tabellen abhängig sind, die im Katalog definiert sind und einem bestimmten Benutzer gehören. (VIEW_COLUMN_USAGE-Rowset)</p></td>
<td><p>VIEW_CATALOG<br />
VIEW_SCHEMA<br />
VIEW_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaViews</strong></p></td>
<td><p>23</p></td>
<td><p>Gibt die im Katalog definierten Sichten zurück, auf die ein bestimmter Benutzer zugreifen kann. (VIEWS-Rowset)</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaViewTableUsage</strong></p></td>
<td><p>25</p></td>
<td><p>Gibt die Tabellen zurück, von denen die angezeigten Tabellen abhängig sind, die im Katalog definiert sind und einem bestimmten Benutzer gehören. (VIEW_TABLE_USAGE-Rowset)</p></td>
<td><p>VIEW_CATALOG<br />
VIEW_SCHEMA<br />
VIEW_NAME</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC-Äquivalent

Paket: **com.ms.wfc.data**

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Konstante</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AdoEnums. Schema. ASSERTs</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. CATALOGs</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. CHARACTERSETS</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. CHECKCONSTRAINTS</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. COLLation</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. COLUMNPRIVILEGES</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. COLUMNS</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. COLUMNSDOMAINUSAGE</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. CONSTRAINTCOLUMNUSAGE</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. CONSTRAINTTABLEUSAGE</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. Cubes</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. DBINFOKEYWORDS</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. DBINFOLITERALS</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. DIMENSIONs</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. FOREIGNKEYS</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. HIERARCHIEs</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. INDEXes</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. KEYCOLUMNUSAGE</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. LEVELS</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. MEASUREs</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. MEMBERS</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. PRIMARy</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. PROCEDURECOLUMNS</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. PROCEDUREPARAMETERS</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. PROCEDURes</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. PROPERTIES</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. PROVIDERSPECIFIC</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. PROVIDERTYPES</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. REFERENTIALCONTRAINTS</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. SCHEMATA</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. sqlLANGUAGEs</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. STATISTICs</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. TableSchema</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. TableSchema-Berechtigungen</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. TABLEs</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. TRANSLATIONS</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. TRUSTEES</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. USAGEPRIVILEGES</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. VIEWCOLUMNUSAGE</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. Schema. VIEWS</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. Schema. VIEWTABLEUSAGE</p></td>
</tr>
</tbody>
</table>

