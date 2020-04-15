---
title: 'SQL: Doğrudan SQL Çağrıları Yapma (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- SQL, direct calls from ODBC
- SQL, calling directly from ODBC
- ODBC, SQL calls
- SQL calls
- direct SQL calls from ODBC
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
ms.openlocfilehash: e2421e047d217fdc7a138509385399fa37d36a1f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374508"
---
# <a name="sql-making-direct-sql-calls-odbc"></a>SQL: Doğrudan SQL Çağrıları Yapma (ODBC)

Bu konu açıklar:

- Doğrudan SQL çağrılarıne ne zaman kullanılır.

- [Veri kaynağına doğrudan SQL aramaları nasıl yapılır.](#_core_making_direct_sql_function_calls)

> [!NOTE]
> Bu bilgiler MFC ODBC sınıfları için geçerlidir. MFC DAO sınıfları ile çalışıyorsanız, DAO Help'de "Microsoft Jet Database Engine SQL ve ANSI SQL karşılaştırması" konusuna bakın.

## <a name="when-to-call-sql-directly"></a><a name="_core_when_to_call_sql_directly"></a>SQL Doğrudan Ne Zaman Çağrılır?

Yeni tablolar oluşturmak, tabloları düşürmek (silmek) için, varolan tabloları değiştirmek, dizinler oluşturmak ve [Veri Kaynağı (ODBC)](../../data/odbc/data-source-odbc.md) şemasını değiştiren diğer SQL işlevlerini gerçekleştirmek için Veritabanı Tanımı Dili 'ni (DDL) kullanarak doğrudan veri kaynağına bir SQL deyimi vermeniz gerekir. Bir tablo için bir kayıt kümesi oluşturmak için bir sihirbaz kullandığınızda (tasarım zamanında), tablonun hangi sütunlarında temsil edeceğini seçebilirsiniz. Bu, programınız derlendikten sonra sizin veya veri kaynağının başka bir kullanıcısının tabloya daha sonra eklemesine izin vermez. Veritabanı sınıfları DDL'yi doğrudan desteklemez, ancak yine de yeni bir sütunu çalışma saatinde dinamik olarak kayıt setinize bağlamak için kod yazabilirsiniz. Bu bağlamanın nasıl yapılacağını öğrenmek için [bkz.](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)

Şemayı veya DDL işlevlerini gerçekleştirmenize olanak tanıyan başka bir aracı değiştirmek için DBMS'nin kendisini kullanabilirsiniz. Kayıtları döndürmeyen önceden tanımlanmış bir sorgu (depolanmış yordam) çağırmak gibi SQL deyimleri göndermek için ODBC işlev çağrılarını da kullanabilirsiniz.

## <a name="making-direct-sql-function-calls"></a><a name="_core_making_direct_sql_function_calls"></a>Doğrudan SQL İşlev Aramaları Yapma

[CDatabase Class](../../mfc/reference/cdatabase-class.md) nesnesini kullanarak doğrudan bir SQL çağrısı yürütebilirsiniz. SQL ekstre dizenizi `CString`(genellikle bir) ayarlayın ve nesnenizin `CDatabase` [CDatabase::ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) üye işlevine geçirin. Normalde kayıtları döndüren bir SQL deyimi göndermek için ODBC işlev çağrılarını kullanırsanız, kayıtlar yoksayılır.

## <a name="see-also"></a>Ayrıca bkz.

[SQL](../../data/odbc/sql.md)
