---
description: 'Şu konuda daha fazla bilgi edinin: SQL: doğrudan SQL çağrıları yapma (ODBC)'
title: 'SQL: Doğrudan SQL Çağrıları Yapma (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- SQL, direct calls from ODBC
- SQL, calling directly from ODBC
- ODBC, SQL calls
- SQL calls
- direct SQL calls from ODBC
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
ms.openlocfilehash: 1cf7f20bf7de777f418c289f06878fa9ae448c12
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124520"
---
# <a name="sql-making-direct-sql-calls-odbc"></a>SQL: Doğrudan SQL Çağrıları Yapma (ODBC)

Bu konuda aşağıdakiler açıklanmaktadır:

- Doğrudan SQL çağrılarının ne zaman kullanılacağı.

- [Veri kaynağına doğrudan SQL çağrıları yapma](#_core_making_direct_sql_function_calls).

> [!NOTE]
> Bu bilgiler MFC ODBC sınıfları için geçerlidir. MFC DAO sınıflarıyla çalışıyorsanız, DAO yardımı 'nda "Microsoft Jet veritabanı altyapısı SQL ve ANSI SQL karşılaştırması" konusuna bakın.

## <a name="when-to-call-sql-directly"></a><a name="_core_when_to_call_sql_directly"></a> SQL 'i doğrudan çağırma

Yeni tablolar oluşturmak, tabloları bırakmak, var olan tabloları değiştirmek, dizinler oluşturmak ve [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md) şemasını DEĞIŞTIREN diğer SQL işlevlerini gerçekleştirmek Için, veritabanı tanım DILI (ddl) kullanarak doğrudan veri KAYNAĞıNA bir SQL ifadesi vermelisiniz. Bir tablo için bir kayıt kümesi oluşturmak üzere bir sihirbaz kullandığınızda (tasarım zamanında), tablodaki hangi sütunların kayıt kümesinde temsil edileceğini seçebilirsiniz. Bu, siz veya veri kaynağı için başka bir kullanıcının tabloya daha sonra, programınız derlendikten sonra eklemesini sağlar. Veritabanı sınıfları doğrudan DDL 'yi desteklemez, ancak çalışma zamanında kayıt kümenize dinamik olarak yeni bir sütun bağlamak için kod yazmaya devam edebilirsiniz. Bu bağlamanın nasıl yapılacağı hakkında bilgi için bkz. [Recordset: dinamik olarak veri sütunlarını bağlama (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

Şemayı veya DDL işlevleri gerçekleştirmenize olanak sağlayan başka bir aracı değiştirmek için DBMS 'yi kullanabilirsiniz. Ayrıca, kayıt döndürmeyen önceden tanımlanmış bir sorgu (saklı yordam) çağırma gibi SQL deyimlerini göndermek için ODBC işlev çağrılarını da kullanabilirsiniz.

## <a name="making-direct-sql-function-calls"></a><a name="_core_making_direct_sql_function_calls"></a> Doğrudan SQL Işlev çağrıları yapma

Bir [CDatabase sınıfı](../../mfc/reference/cdatabase-class.md) nesnesi kullanarak doğrudan bir SQL çağrısı yürütebilirsiniz. SQL ifade dizenizi ayarlayın (genellikle bir içinde `CString` ) ve nesnenizin [CDatabase:: ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) üye işlevine geçirin `CDatabase` . Normalde kayıtları döndüren bir SQL ifadesini göndermek için ODBC işlev çağrıları kullanırsanız, kayıtlar yok sayılır.

## <a name="see-also"></a>Ayrıca bkz.

[SQL](../../data/odbc/sql.md)
