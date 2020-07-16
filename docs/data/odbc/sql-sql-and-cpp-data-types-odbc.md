---
title: 'SQL: SQL ve C++ Veri Türleri (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
ms.openlocfilehash: 70796db02f8ff3fcfd67694fb596722664e8f904
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404261"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL: SQL ve C++ Veri Türleri (ODBC)

> [!NOTE]
> Bu bilgiler MFC ODBC sınıfları için geçerlidir. MFC DAO sınıflarıyla çalışıyorsanız, DAO yardımı 'nda "Microsoft Jet veritabanı altyapısı SQL ve ANSI SQL karşılaştırması" konusuna bakın.

Aşağıdaki tabloda ANSI SQL veri türleri C++ veri türleriyle eşlenir. Bu, [ODBC Programmer 'ın başvuru](/sql/odbc/reference/odbc-programmer-s-reference) belgelerinin ek D ' de verilen C dil bilgilerini azaltır. Sihirbazlar, sizin için çoğu veri türü eşlemesini yönetir. Sihirbaz kullanmıyorsanız, alan değişimi kodunu el ile yazmanıza yardımcı olması için eşleme bilgilerini kullanabilirsiniz.

### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>C++ veri türleriyle eşlenen ANSI SQL veri türleri

|ANSI SQL veri türü|C++ veri türü|
|------------------------|---------------------|
|**CHAR**|`CString`|
|**KATEGORI**|`CString`1|
|**Small**|**int**|
|**GERÇEK**|**float**|
|**GIR**|**long**|
|**FLOAT**|**Çift**|
|**ÇIFT**|**Çift**|
|**RAKAMLARDAN**|`CString`1|
|**VARCHAR**|`CString`|
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|
|**SÜRÜMLERI**|**BOOL**|
|**Iç**|**BYTE**|
|**BIGıNT**|`CString`1|
|**Ý**|`CByteArray`|
|**IKILI**|`CByteArray`|
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|
|**GÜNCEL**|`CTime`, `CString`|
|**IŞıNıZDA**|`CTime`, `CString`|
|**ILIŞKIN**|`CTime`, `CString`|

1. **DECIMAL** **NUMERIC** `CString` **Sql_c_char** varsayılan ODBC aktarım türü olduğundan, ANSI DECIMAL ve sayısal eşleme.

2. 255 karakterlerin ötesindeki karakter verileri, ile eşlendiğinde varsayılan olarak kesilir `CString` . *NMaxLength* bağımsız değişkenini açıkça ayarlayarak kesme uzunluğunu genişletebilirsiniz `RFX_Text` .

3. 255 karakter dışında ikili veriler, ile eşlendiğinde varsayılan olarak kesilir `CByteArray` . *NMaxLength* bağımsız değişkenini açıkça ayarlayarak kesme uzunluğunu genişletebilirsiniz `RFX_Binary` .

ODBC imleç kitaplığını kullanmıyorsanız, Microsoft SQL Server ODBC sürücüsünü ve MFC ODBC veritabanı sınıflarını kullanarak iki veya daha fazla uzun değişken uzunluklu alanı güncelleştirmeye çalışırken bir sorunla karşılaşabilirsiniz. ODBC türleri, **SQL_LONGVARCHAR** ve **SQL_LONGVARBINARY**, metin ve görüntü SQL Server türleriyle eşlenir. `CDBException`Aynı çağrısındaki iki veya daha fazla değişken uzunluklu alanı güncelleştirirseniz oluşturulur `CRecordset::Update` . Bu nedenle, birden çok uzun sütunu eşzamanlı olarak güncelleştirme `CRecordset::Update` . Birden çok uzun sütunu aynı anda ODBC API 'siyle güncelleştirebilirsiniz `SQLPutData` . ODBC imleç kitaplığını da kullanabilirsiniz, ancak bu, imleçleri destekleyen ve imleç kitaplığına gerek olmayan SQL Server sürücüsü gibi sürücüler için önerilmez.

MFC ODBC veritabanı sınıfları ve Microsoft SQL Server ODBC sürücüsü ile ODBC imleç kitaplığını kullanıyorsanız, **ASSERT** `CDBException` `CRecordset::Update` çağrısı izleyen bir çağrı varsa, ile birlikte bir onaylama gerçekleşmeyebilir `CRecordset::Requery` . Bunun yerine, `CRecordset::Close` ve yerine çağırın `CRecordset::Open` `CRecordset::Requery` . SQL Server ve SQL Server ODBC sürücüsü yerel imleçler için yerel destek sağladığından ve ODBC imleç kitaplığı gerekli olmadığından, başka bir çözüm ODBC imleç kitaplığını kullanmaz.

## <a name="see-also"></a>Ayrıca bkz.

[SQL](../../data/odbc/sql.md)<br/>
[SQL: doğrudan SQL çağrıları yapma (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
