---
title: 'SQL: Doğrudan SQL çağrıları yapma (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- SQL, direct calls from ODBC
- SQL, calling directly from ODBC
- ODBC, SQL calls
- SQL calls
- direct SQL calls from ODBC
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2201a8936c1f28221bfcb628139a979e042715b9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079226"
---
# <a name="sql-making-direct-sql-calls-odbc"></a>SQL: Doğrudan SQL Çağrıları Yapma (ODBC)

Bu konu şunları açıklar:

- Doğrudan SQL kullanmak ne zaman çağırır.

- [Çağıran veri kaynağına nasıl SQL doğrudan yaptığınız](#_core_making_direct_sql_function_calls).

> [!NOTE]
>  Bu bilgiler, MFC ODBC sınıflarına uygulanır. MFC DAO sınıflarına ile çalışıyorsanız, "Karşılaştırma, Microsoft Jet veritabanı altyapısı SQL ve ANSI SQL" DAO Yardım konusuna bakın.

##  <a name="_core_when_to_call_sql_directly"></a> SQL'i doğrudan çağırmak ne zaman

Yeni tablolar oluşturmak için (Sil) tabloları kaldırın, varolan tablolarda alter, dizinler oluşturma ve değiştirme diğer SQL işlevleri gerçekleştirmek [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md) şema gerekir dağıttığınız bir SQL deyimi kullanarak veritabanı doğrudan veri kaynağına Tanım Dili (DDL). (Tasarım zamanında) bir tablo için bir kayıt kümesi oluşturmak için bir sihirbaz kullandığınızda, kümenize temsil etmek için tablonun hangi sütunlarının seçebilirsiniz. Bu, siz veya başka bir kullanıcı veri kaynağının tablosuna ekleme daha sonra programınızı derlendikten sonra sütunlar için izin vermez. Veritabanı sınıfları DDL doğrudan desteklemez, ancak yine de yeni bir sütun kümenize çalışma zamanında dinamik olarak bağlama için kod yazabilirsiniz. Bu bağlama yapma hakkında daha fazla bilgi için bkz: [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

DBMS, şema veya DDL işlevlerini gerçekleştirmenize olanak tanıyan başka bir aracı değiştirmek için kullanabilirsiniz. ODBC işlev çağrıları kayıtları döndürmeyen önceden tanımlanmış sorgu (saklı yordam) arama gibi SQL deyimleri göndermek için de kullanabilirsiniz.

##  <a name="_core_making_direct_sql_function_calls"></a> Doğrudan SQL işlev çağrıları yapma

Doğrudan kullanarak bir SQL çağrı yürütebilir bir [CDatabase sınıfı](../../mfc/reference/cdatabase-class.md) nesne. SQL deyimi dizenizi ayarlayın (genellikle bir `CString`) ve geçirin [CDatabase:: Executesql'den](../../mfc/reference/cdatabase-class.md#executesql) üye işlevini, `CDatabase` nesne. Normalde kayıtlar döndüren bir SQL deyimi göndermek için ODBC işlev çağrıları kullanırsanız, kayıtlara göz ardı edilir.

## <a name="see-also"></a>Ayrıca Bkz.

[SQL](../../data/odbc/sql.md)