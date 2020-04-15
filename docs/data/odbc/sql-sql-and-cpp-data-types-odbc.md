---
title: 'SQL: SQL ve C++ Veri Türleri (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
ms.openlocfilehash: cffe44b832ac1eb28d368072b8f0e92ea9f57feb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374472"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL: SQL ve C++ Veri Türleri (ODBC)

> [!NOTE]
> Bu bilgiler MFC ODBC sınıfları için geçerlidir. MFC DAO sınıfları ile çalışıyorsanız, DAO Help'de "Microsoft Jet Database Engine SQL ve ANSI SQL karşılaştırması" konusuna bakın.

Aşağıdaki tablo, ANSI SQL veri türlerini C++ veri türleri ile eşler. Bu, MSDN Kitaplığı CD'sindeki *ODBC SDK* *Programcı Referansı'nın* Ek D'sinde verilen C dil bilgilerini genişletir. Sihirbazlar sizin için çoğu veri türü eşleme yönetir. Sihirbaz kullanmıyorsanız, alan değişim kodunu el ile yazmanıza yardımcı olmak için eşleme bilgilerini kullanabilirsiniz.

### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>ANSI SQL Veri Türleri C++ Veri Türlerine Eşlendi

|ANSI SQL veri türü|C++ veri türü|
|------------------------|---------------------|
|**Char**|`CString`|
|**On -da -lık**|`CString`1|
|**Smallint**|**int**|
|**Gerçek**|**float**|
|**Tamsayı**|**long**|
|**Float**|**double**|
|**Çift**|**double**|
|**Sayısal**|`CString`1|
|**Varchar**|`CString`|
|**LONGVARCHAR**|`CLongBinary`, `CString` 2, 2|
|**Bit**|**Bool**|
|**Tinyint**|**BYTE**|
|**Bigint**|`CString`1|
|**Ikili**|`CByteArray`|
|**Varbinary**|`CByteArray`|
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3,|
|**Tarih**|`CTime`, `CString`|
|**Zaman**|`CTime`, `CString`|
|**Zaman damgası**|`CTime`, `CString`|

1. ANSI **DECIMAL** ve **NUMERIC** harita çünkü `CString` **SQL_C_CHAR** varsayılan ODBC aktarım türüdür.

2. 255 karakter dışındaki karakter verileri, `CString`eşlendiğinde varsayılan olarak kesilir. *NMaxLength* bağımsız değişkenini `RFX_Text`açıkça ayarlayarak kesilme uzunluğunu uzatabilirsiniz.

3. 255 karakterin ötesindeki ikili `CByteArray`veriler, eşlendiğinde varsayılan olarak kesilir. *NMaxLength* bağımsız değişkenini `RFX_Binary`açıkça ayarlayarak kesilme uzunluğunu uzatabilirsiniz.

ODBC imleç kitaplığını kullanmıyorsanız, Microsoft SQL Server ODBC sürücüsünü ve MFC ODBC veritabanı sınıflarını kullanarak iki veya daha fazla uzun değişken uzunlukta alanı güncelleştirmeye çalışırken bir sorunla karşılaşabilirsiniz. ODBC türleri, **SQL_LONGVARCHAR** ve **SQL_LONGVARBINARY,** metin ve görüntü SQL Server türleri için eş. Aynı `CDBException` çağrıda iki veya daha fazla uzun değişken uzunlukta alanı `CRecordset::Update`güncellerseniz A atılır. Bu nedenle, aynı anda birden `CRecordset::Update`çok uzun sütun güncelleştirmeyin. ODBC API `SQLPutData`ile aynı anda birden çok uzun sütunu güncelleştirebilirsiniz. ODBC imleç kitaplığını da kullanabilirsiniz, ancak bu imleçleri destekleyen ve imleç kitaplığını gerekmeyen SQL Server sürücüsü gibi sürücüler için önerilmez.

MFC ODBC veritabanı sınıfları ve Microsoft SQL Server ODBC sürücüsü ile ODBC imleç kitaplığını `CDBException` kullanıyorsanız, `CRecordset::Update` bir if `CRecordset::Requery`acall ile birlikte bir **Assert** ' da bir çağrı yı takip edebilir. Bunun yerine, `CRecordset::Open` arama `CRecordset::Requery` `CRecordset::Close` ve yerine . SQL Server ve SQL Server ODBC sürücüsü imleçler için yerel destek sağladığından ve ODBC imleç kitaplığı gerekli olmadığından, başka bir çözüm de ODBC imleç kitaplığını kullanmamaktır.

## <a name="see-also"></a>Ayrıca bkz.

[SQL](../../data/odbc/sql.md)<br/>
[SQL: Doğrudan SQL Çağrıları Yapma (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
