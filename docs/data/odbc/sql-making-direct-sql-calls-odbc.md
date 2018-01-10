---
title: "SQL: Doğrudan SQL çağrıları yapma (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- SQL, direct calls from ODBC
- SQL, calling directly from ODBC
- ODBC, SQL calls
- SQL calls
- direct SQL calls from ODBC
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4c5debd5017c2c9c9cad240f831fdf6e02be98ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="sql-making-direct-sql-calls-odbc"></a>SQL: Doğrudan SQL Çağrıları Yapma (ODBC)
Bu konuda açıklanmaktadır:  
  
-   Doğrudan SQL kullanmak ne zaman çağırır.  
  
-   [Çağıran veri kaynağına nasıl SQL doğrudan hale](#_core_making_direct_sql_function_calls).  
  
> [!NOTE]
>  Bu bilgiler, MFC ODBC sınıfları için geçerlidir. MFC DAO sınıfları ile çalışıyorsanız, "Karşılaştırma, Microsoft Jet veritabanı altyapısı SQL ve ANSI SQL" DAO Yardım konusuna bakın.  
  
##  <a name="_core_when_to_call_sql_directly"></a>SQL doğrudan çağırmak ne zaman  
 Yeni tablo oluşturmak için (silme) tabloları kaldırın, var olan tabloları değiştirmek, dizinler oluşturmak ve değiştirmek diğer SQL işlevleri gerçekleştirmek [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md) şema gerekir dağıttığınız bir SQL deyimi veritabanı kullanarak doğrudan veri kaynağına Tanım Dili (DDL). Bir tablo için bir kayıt kümesi (tasarım zamanında) oluşturmak için bir sihirbaz kullandığınızda, kayıt kümesinde temsil etmek için tablonun hangi sütunlarının seçebilirsiniz. Bu, siz veya başka bir kullanıcı veri kaynağının tabloya daha sonra programınızı derlendikten sonra Sütun Ekle için izin vermez. Veritabanı sınıfları DDL doğrudan desteklemez, ancak yine de yeni bir sütun kümenize çalışma zamanında dinamik olarak bağlamak için kod yazabilirsiniz. Bu bağlama yapma hakkında daha fazla bilgi için bkz: [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 DBMS, şema veya DDL işlevleri gerçekleştirmenizi sağlayan başka bir aracı değiştirmek için kullanabilirsiniz. ODBC işlev çağrılarını kayıtları döndürmeyen önceden tanımlanmış sorgu (saklı yordam) çağırma gibi SQL deyimlerini göndermek için de kullanabilirsiniz.  
  
##  <a name="_core_making_direct_sql_function_calls"></a>Doğrudan SQL işlev çağrıları yapma  
 Doğrudan SQL kullanarak çağrı yürütebilir bir [CDatabase sınıfı](../../mfc/reference/cdatabase-class.md) nesnesi. SQL deyimi dizenizi ayarlayın (genellikle bir `CString`) ve ona geçirin [CDatabase::ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) üye işlevini, `CDatabase` nesnesi. Normalde kayıtları döndüren bir SQL deyimi göndermek için ODBC işlev çağrılarını kullanırsanız kayıtları göz ardı edilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SQL](../../data/odbc/sql.md)