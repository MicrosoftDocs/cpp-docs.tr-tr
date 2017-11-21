---
title: "Kayıt görünümleri (MFC veri erişimi) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC [C++], record views
- ODBC recordsets [C++], record views
- databases [C++], record views
- record views [C++]
- forms [C++], data access tasks
ms.assetid: 562122d9-01d8-4284-acf6-ea109ab0408d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 38c5d65e89aa4fb76ff96fa82cd52e42475e2353
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="record-views--mfc-data-access"></a>Kayıt görünümleri (MFC veri erişimi)
Bu bölüm, yalnızca MFC ODBC sınıfları için geçerlidir. OLE DB kayıt görünümleri hakkında daha fazla bilgi için bkz: [COleDBRecordView](../mfc/reference/coledbrecordview-class.md) ve [kullanarak OLE DB kayıt görünümleri](../data/oledb/using-ole-db-record-views.md).  
  
 Form tabanlı veri erişimi uygulamaları desteklemek için sınıf kitaplığı SAX [CRecordView](../mfc/reference/crecordview-class.md). Kayıt görünümü, denetimleri doğrudan alan veri üyeleri için eşlenmiş bir form görüntüleme nesnesidir bir [kayıt kümesi](../data/odbc/recordset-odbc.md) nesne (ve karşılık gelen sütunlara bir sorgu sonucu ya da veri kaynağında tablo için dolaylı olarak). İster kendi temel sınıfının [Cformview'yu](../mfc/reference/cformview-class.md), `CRecordView` iletişim şablon kaynağında dayanır.  
  
## <a name="form-uses"></a>Form kullanır  
 Formları, çeşitli veri erişim görevleri için yararlıdır:  
  
-   Veri girme  
  
-   Veri salt okunur incelenmesi gerçekleştirme  
  
-   Verileri güncelleştirme  
  
## <a name="further-reading-about-record-views"></a>Kayıt görünümleri hakkında daha fazla bilgi  
 Konulardaki malzeme ODBC tabanlı ve DAO tabanlı sınıflar için geçerlidir. Kullanım `CRecordView` ODBC için ve `CDaoRecordView` DAO için.  
  
 Konular şunlardır:  
  
-   [Kayıt görünümü sınıflarının özellikleri](../data/features-of-record-view-classes-mfc-data-access.md)  
  
-   [Kayıt görünümleri için veri değişimi](../data/data-exchange-for-record-views-mfc-data-access.md)  
  
-   [Kayıt görünümü ile çalışırken sizin rolünüz](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)  
  
-   [Tasarlama ve kayıt görünümü oluşturma](../data/designing-and-creating-a-record-view-mfc-data-access.md)  
  
-   [Kayıt görünümünü kullanma](../data/using-a-record-view-mfc-data-access.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri erişimi (MFC/ATL) programlama](../data/data-access-programming-mfc-atl.md)   
 [ODBC sürücü listesi](../data/odbc/odbc-driver-list.md)