---
title: 'SQL: SQL ve C++ Veri Türleri (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
ms.openlocfilehash: 1c1ce908b5c8d345906d49adc79e322225ed49f5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212621"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL: SQL ve C++ Veri Türleri (ODBC)

> [!NOTE]
>  Bu bilgiler MFC ODBC sınıfları için geçerlidir. MFC DAO sınıflarıyla çalışıyorsanız, DAO yardımı 'nda "Microsoft Jet veritabanı altyapısı SQL ve ANSI SQL karşılaştırması" konusuna bakın.

Aşağıdaki tablo, ANSI SQL veri türlerini C++ veri türlerine eşler. Bu, MSDN Kitaplığı CD 'sindeki {1 & gt; *ODBC SDK* *programcısı* & lt; 1}. Sihirbazlar, sizin için çoğu veri türü eşlemesini yönetir. Sihirbaz kullanmıyorsanız, alan değişimi kodunu el ile yazmanıza yardımcı olması için eşleme bilgilerini kullanabilirsiniz.

### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>C++ Veri TÜRLERIYLE eşlenen ANSI SQL veri türleri

|ANSI SQL veri türü|C++veri türü|
|------------------------|---------------------|
|**CHAR**|`CString`|
|**KATEGORI**|`CString` 1|
|**Small**|**int**|
|**GERÇEK**|**float**|
|**GIR**|**long**|
|**FLOAT**|**double**|
|**ÇIFT**|**double**|
|**RAKAMLARDAN**|`CString` 1|
|**VARCHAR**|`CString`|
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|
|**SÜRÜMLERI**|**BOOL**|
|**Iç**|**BAYT**|
|**BIGıNT**|`CString` 1|
|**Ý**|`CByteArray`|
|**IKILI**|`CByteArray`|
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|
|**DATE**|`CTime`, `CString`|
|**TIME**|`CTime`, `CString`|
|**ILIŞKIN**|`CTime`, `CString`|

1. **Sql_c_char** varsayılan ODBC aktarım türü olduğundan, ANSI **DECIMAL** ve **sayısal** eşleme `CString`.

2. 255 karakterlerin ötesindeki karakter verileri, `CString`ile eşlendiğinde varsayılan olarak kesilir. `RFX_Text`*nMaxLength* bağımsız değişkenini açıkça ayarlayarak kesme uzunluğunu genişletebilirsiniz.

3. 255 karakter dışında ikili veriler, `CByteArray`ile eşlendiğinde varsayılan olarak kesilir. `RFX_Binary`*nMaxLength* bağımsız değişkenini açıkça ayarlayarak kesme uzunluğunu genişletebilirsiniz.

ODBC imleç kitaplığını kullanmıyorsanız, Microsoft SQL Server ODBC sürücüsünü ve MFC ODBC veritabanı sınıflarını kullanarak iki veya daha fazla uzun değişken uzunluklu alanı güncelleştirmeye çalışırken bir sorunla karşılaşabilirsiniz. ODBC türleri, **SQL_LONGVARCHAR** ve **SQL_LONGVARBINARY**, metin ve görüntü SQL Server türleriyle eşlenir. Aynı `CRecordset::Update`iki veya daha fazla değişken uzunlukta alanı güncelleştirirseniz `CDBException` oluşturulur. Bu nedenle, birden çok uzun sütunu eşzamanlı olarak `CRecordset::Update`güncelleştirmeyin. Birden çok uzun sütunu eşzamanlı olarak ODBC API `SQLPutData`güncelleştirebilirsiniz. ODBC imleç kitaplığını da kullanabilirsiniz, ancak bu, imleçleri destekleyen ve imleç kitaplığına gerek olmayan SQL Server sürücüsü gibi sürücüler için önerilmez.

MFC ODBC veritabanı sınıfları ve Microsoft SQL Server ODBC sürücüsü ile ODBC imleç kitaplığını kullanıyorsanız, `CRecordset::Update` çağrısı `CRecordset::Requery`için bir çağrıyı izleyen bir `CDBException` ile birlikte bir **onaylama** gerçekleşmeyebilir. Bunun yerine, `CRecordset::Requery`yerine `CRecordset::Close` ve `CRecordset::Open` çağırın. SQL Server ve SQL Server ODBC sürücüsü yerel imleçler için yerel destek sağladığından ve ODBC imleç kitaplığı gerekli olmadığından, başka bir çözüm ODBC imleç kitaplığını kullanmaz.

## <a name="see-also"></a>Ayrıca bkz.

[SQL](../../data/odbc/sql.md)<br/>
[SQL: Doğrudan SQL Çağrıları Yapma (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
