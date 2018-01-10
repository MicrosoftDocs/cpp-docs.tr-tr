---
title: "Kayıt görünümü (MFC veri erişimi) ile çalışırken sizin rolünüz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- record views, customizing default code
- MFC, record views
ms.assetid: 691e89a5-ff21-4ca3-9278-69d4678288bb
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 03d64715f3bdfb6028fdb039451d4b4b004a059e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="your-role-in-working-with-a-record-view--mfc-data-access"></a>Kayıt görünümü (MFC veri erişimi) ile çalışırken sizin rolünüz
Aşağıdaki tabloda, genellikle kayıt görünümü ile çalışmak için ne gerekir ve framework sizin için ne yaptığını gösterir.  
  
### <a name="working-with-a-record-view-you-and-the-framework"></a>Kayıt görünümü ile çalışırken: siz ve Framework  
  
|Bunun için,|Çerçeve|  
|---------|-------------------|  
|Form tasarlamak için Visual C++ iletişim kutusu Düzenleyicisi'ni kullanın.|Bir iletişim kutusu şablon kaynağı denetimleriyle oluşturur.|  
|Kullanım [MFC Uygulama Sihirbazı'nı](../mfc/reference/database-support-mfc-application-wizard.md) türetilmiş sınıfları oluşturmak için [CRecordView](../mfc/reference/crecordview-class.md) ve [CRecordset](../mfc/reference/crecordset-class.md).|Sınıflar için yazar.|  
|Kayıt görünümü denetimlerini kayıt kümesi alan veri üyeleri için eşleyin.|DDX denetimleri ve kayıt kümesi alanları arasında sağlar.|  
||Varsayılan için komut işleyicileri sağlar **taşıma ilk**, **taşıma son**, **taşıma sonraki**, ve **taşıma önceki** komutların menülerden veya araç düğmeler.|  
||Veri kaynağına değişiklikleri güncelleştirir.|  
|[İsteğe bağlı] Liste kutuları veya birleşik giriş kutuları veya diğer denetimleri ikinci kayıt kümesinden verilerle doldurmak için kod yazma.||  
|[İsteğe bağlı] Herhangi bir özel doğrulama kodunu yazın.||  
|[İsteğe bağlı] Kayıtlarını eklemek veya silmek için kod yazın.||  
  
 Form tabanlı programlama bir veritabanıyla çalışmak için yalnızca bir yaklaşımdır. Başka bir kullanıcı arabirimi veya herhangi bir kullanıcı arabirimi kullanarak uygulamaları hakkında daha fazla bilgi için bkz: [MFC: belgeler ve görünümler ile veritabanı sınıflarını kullanarak](../data/mfc-using-database-classes-with-documents-and-views.md) ve [MFC: olmadan veritabanı sınıflarını belgeleri kullanarak ve görünümleri](../data/mfc-using-database-classes-without-documents-and-views.md). Veritabanı kayıtlarını görüntülemeye alternatif yaklaşımlar için bkz: sınıfları [CListView](../mfc/reference/clistview-class.md) ve [CTreeView](../mfc/reference/ctreeview-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)   
 [ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)