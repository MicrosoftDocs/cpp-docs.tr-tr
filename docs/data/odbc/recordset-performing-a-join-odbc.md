---
title: 'Kayıt kümesi: bir birleşim gerçekleştirme (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- joins [C++], in recordsets
- data binding [C++], recordset columns
- recordsets [C++], binding data
- data binding [C++], columns in recordsets
- filters [C++], join conditions for recordsets
- ODBC recordsets [C++], joins
- recordsets [C++], joining tables
ms.assetid: ca720900-a156-4780-bf01-4293633bea64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0be740a57f5c455b971dd23575401c666bf0723c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-performing-a-join-odbc"></a>Kayıt Kümesi: Birleşim Gerçekleştirme (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
## <a name="what-a-join-is"></a>Ne bir birleşim  
 Birleştirme işlemi, ortak bir veri erişim görevi, bir tek kayıt kümesi nesnesi kullanarak birden fazla tablodan veri çalışmanıza olanak sağlar. İki veya daha fazla tabloları birleştirme her tablodan sütun içerebilir ancak uygulamanız için tek bir tablo olarak görünen bir kayıt kümesi verir. Tüm tablolar, ancak bazı durumlarda SQL tüm sütunları join bazen kullanır **seçin** JOIN yan tümcesinde her tablodaki sütunların yalnızca bazılarını kullanır. Veritabanı sınıfları salt okunur birleştirmeler güncelleştirilebilir değil birleştirmeler destekler.  
  
 Birleştirilmiş tablolardaki sütunları içeren kayıtları seçmek için aşağıdaki öğeleri gerekir:  
  
-   Birleştirilen tüm tabloların adlarını içeren bir tablo listesi.  
  
-   Tüm katılımcı sütunlarının adlarını içeren bir sütun listesi. Aynı ada sahip ancak farklı tablolardan gelen sütunlar tablo adıyla yetkili olan.  
  
-   Bir filtre (SQL **burada** yan tümcesi) tabloları birleştirilir sütunları belirtir. Bu filtre biçimdedir "Table1.KeyCol Table2.KeyCol =" ve gerçekte birleştirme gerçekleştirir.  
  
 Birden çok sütun çiftleri, SQL anahtar sözcüğüyle birleştirilmiş her çifti eşitleyerek tarafından aynı yolla ikiden fazla tablo katılabilirsiniz **ve**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: bir sınıf bir önceden tanımlanmış sorgu için bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)   
 [Kayıt kümesi: bir sınıf bir tablo için bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [Kayıt kümesi: Bir Kayıt Kümesinde Yeniden Sorgulama (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)