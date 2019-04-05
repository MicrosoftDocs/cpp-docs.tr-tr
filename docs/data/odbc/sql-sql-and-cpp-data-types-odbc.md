---
title: 'SQL: SQL ve C++ veri türleri (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
ms.openlocfilehash: 3efa36342b7d16968113acd818a7a1386e4cefcc
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024354"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL: SQL ve C++ veri türleri (ODBC)

> [!NOTE]
>  Bu bilgiler, MFC ODBC sınıflarına uygulanır. MFC DAO sınıflarına ile çalışıyorsanız, "Karşılaştırma, Microsoft Jet veritabanı altyapısı SQL ve ANSI SQL" DAO Yardım konusuna bakın.

Aşağıdaki tabloda, ANSI SQL veri türleri için C++ veri türleri eşler. Bu ek D içinde verilen C dil bilgileri artırmaktadır *ODBC SDK* *Programcının Başvurusu* MSDN Kitaplığı CD'sindeki. Sihirbazlar, çoğu veri türü eşlemesi yönetin. Bir sihirbaz kullanmazsanız, el ile alan exchange kod yazmanıza yardımcı olmak için eşleme bilgilerini kullanabilirsiniz.

### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>C++ veri türleri için eşlenen ANSI SQL veri türleri

|ANSI SQL veri türü|C++ veri türü|
|------------------------|---------------------|
|**CHAR**|`CString`|
|**DECIMAL**|`CString` 1.|
|**TAMSAYI**|**int**|
|**GERÇEK**|**float**|
|**INTEGER**|**long**|
|**KAYAN NOKTA**|**çift**|
|**ÇİFT**|**çift**|
|**NUMERIC**|`CString` 1.|
|**VARCHAR**|`CString`|
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|
|**BIT**|**BOOL**|
|**MİNİ TAMSAYI**|**BYTE**|
|**BIGINT**|`CString` 1.|
|**İKİLİ**|`CByteArray`|
|**VARBINARY**|`CByteArray`|
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|
|**DATE**|`CTime`, `CString`|
|**SAAT**|`CTime`, `CString`|
|**ZAMAN DAMGASI**|`CTime`, `CString`|

1. ANSI **ondalık** ve **sayısal** eşleme `CString` çünkü **SQL_C_CHAR** varsayılan ODBC aktarım türü.

2. 255 karakteri aşan karakter veri eşleştirildiğinde varsayılan olarak kısaltılır `CString`. Kesme uzunluğunu açıkça ayarlayarak genişletebileceğiniz *nMaxLength* bağımsız değişkeni `RFX_Text`.

3. 255 karakteri aşan ikili veri eşleştirildiğinde varsayılan olarak kısaltılır `CByteArray`. Kesme uzunluğunu açıkça ayarlayarak genişletebileceğiniz *nMaxLength* bağımsız değişkeni `RFX_Binary`.

ODBC imleç kitaplığı kullanmıyorsanız, iki güncellemeye çalışırken veya Microsoft SQL Server ODBC sürücüsü ve MFC ODBC veritabanı sınıfları kullanarak daha fazla değişken uzunluklu uzun alan bir sorunla karşılaşabilirsiniz. ODBC türleri **SQL_LONGVARCHAR** ve **SQL_LONGVARBINARY**eşlemek için metin ve resim SQL Server türleri. A `CDBException` iki veya daha fazla değişken uzunlukta uzun alanlar için aynı çağrıda güncelleştirirseniz durum `CRecordset::Update`. Bu nedenle, aynı anda birden çok uzun sütun güncelleştirmez `CRecordset::Update`. ODBC API ile aynı anda birden çok uzun sütun güncelleştirebilirsiniz `SQLPutData`. ODBC imleç kitaplığı da kullanabilirsiniz, ancak bu imleçler destekleyen ve imleç kitaplığı gerekmeyen sürücüler için SQL Server sürücüsünü gibi önerilmez.

MFC ODBC veritabanı sınıfları ve Microsoft SQL Server ODBC sürücüsü ile ODBC imleç kitaplığı kullanıyorsanız bir **ASSERT** ile birlikte oluşabilir bir `CDBException` çağrısı ise `CRecordset::Update` takip `CRecordset::Requery`. Bunun yerine çağrı `CRecordset::Close` ve `CRecordset::Open` yerine `CRecordset::Requery`. SQL Server ve SQL Server ODBC sürücüsü yerel destek işaretçiler için yerel olarak sağlar ve ODBC imleç kitaplığı gerekli değildir çünkü ODBC imleç kitaplığını kullanma başka bir çözümdür.

## <a name="see-also"></a>Ayrıca bkz.

[SQL](../../data/odbc/sql.md)<br/>
[SQL: Doğrudan SQL çağrıları yapma (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)