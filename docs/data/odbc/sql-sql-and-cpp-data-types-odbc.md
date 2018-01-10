---
title: "SQL: SQL ve C++ veri türleri (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 14afd27887368f07610fb1315d7b573c09382c49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL: SQL ve C++ Veri Türleri (ODBC)
> [!NOTE]
>  Bu bilgiler, MFC ODBC sınıfları için geçerlidir. MFC DAO sınıfları ile çalışıyorsanız, "Karşılaştırma, Microsoft Jet veritabanı altyapısı SQL ve ANSI SQL" DAO Yardım konusuna bakın.  
  
 Aşağıdaki tabloda ANSI SQL veri türleri için C++ veri türleri eşler. Bu ek D içinde verilen C dil bilgileri güçlendirir *ODBC SDK* *Programcının Başvurusu* MSDN Kitaplığı CD'sindeki. Sihirbazlar, çoğu veri türü eşlemesi yönetin. Sihirbaz kullanmazsanız, alan değişim kodunu el ile yazmanıza yardım etmek için eşleme bilgilerini kullanabilirsiniz.  
  
### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>C++ veri türleri ile eşlenmiş ANSI SQL veri türleri  
  
|ANSI SQL veri türü|C++ veri türü|  
|------------------------|---------------------|  
|**CHAR**|`CString`|  
|**ONDALIK**|`CString` 1|  
|**TAMSAYI**|`int`|  
|`REAL`|**float**|  
|**TAMSAYI**|**long**|  
|**KAYAN NOKTA**|**double**|  
|**ÇİFT**|**double**|  
|**SAYISAL**|`CString` 1|  
|**VARCHAR**|`CString`|  
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|  
|**BIT**|**BOOL**|  
|**MİNİ TAMSAYI**|**BAYT**|  
|**BIGINT**|`CString` 1|  
|**İKİLİ**|`CByteArray`|  
|**VARBINARY**|`CByteArray`|  
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|  
|**TARİH**|`CTime`, `CString`|  
|**SAAT**|**CTime, CString**|  
|**ZAMAN DAMGASI**|**CTime, CString**|  
  
 1. ANSI **ondalık** ve **sayısal** Eşle `CString` çünkü **SQL_C_CHAR** varsayılan ODBC aktarım türü.  
  
 2. 255 karakteri aşan karakter veri eşlenmiş zaman varsayılan olarak kısaltılır `CString`. Açıkça ayarlayarak kesme uzunluğunu genişletebilirsiniz `nMaxLength` bağımsız değişkeni `RFX_Text`.  
  
 3. 255 karakteri aşan ikili veri eşlenmiş zaman varsayılan olarak kısaltılır `CByteArray`. Açıkça ayarlayarak kesme uzunluğunu genişletebilirsiniz `nMaxLength` bağımsız değişkeni `RFX_Binary`.  
  
 ODBC imleç kitaplığı kullanmıyorsanız, iki güncelleştirmeye çalışırken veya Microsoft SQL Server ODBC sürücüsü MFC ODBC veritabanı sınıfları ile daha fazla değişken uzunlukta uzun alanları bir sorunla karşılaşabilirsiniz. ODBC türleri **SQL_LONGVARCHAR** ve **SQL_LONGVARBINARY**eşlemek için metin ve resim SQL Server türleri. A `CDBException` iki veya daha fazla değişken uzunlukta uzun alanları aynı çağrısında güncelleştirirseniz durum `CRecordset::Update`. Bu nedenle, aynı anda birden çok uzun sütun güncelleştirmeyi `CRecordset::Update`. ODBC API ile aynı anda birden çok uzun sütun güncelleştirebilirsiniz **SQLPutData**. ODBC imleç kitaplığı de kullanabilirsiniz, ancak bu imleçleri desteklemez ve imleç kitaplığı gerekmez sürücüleri için SQL Server sürücüsü gibi önerilmez.  
  
 ODBC imleç kitaplığı MFC ODBC veritabanı sınıfları ve Microsoft SQL Server ODBC sürücüsü ile kullanıyorsanız, bir **ASSERT** ile birlikte oluşabilecek bir `CDBException` yapılan bir çağrı varsa `CRecordset::Update` yapılan bir çağrı izleyen `CRecordset::Requery`. Bunun yerine, çağrı `CRecordset::Close` ve `CRecordset::Open` yerine `CRecordset::Requery`. ODBC imleç kitaplığı SQL Server ve SQL Server ODBC sürücüsü yerel destek imleçler için yerel olarak sağlar ve ODBC imleç kitaplığı gerekli değildir çünkü kullanmamanız başka bir çözümdür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SQL](../../data/odbc/sql.md)   
 [SQL: Doğrudan SQL Çağrıları Yapma (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)