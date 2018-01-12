---
title: "OLE uygulamaları oluşturmak için işlem dizisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE applications [MFC], creating
- OLE applications [MFC]
- applications [OLE], creating
- applications [OLE]
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: db3b5b9a5f4f62fa71cffa37b30a89aee41fe56f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="sequence-of-operations-for-creating-ole-applications"></a>OLE Uygulamaları Oluşturmak için İşlem Dizisi
Aşağıdaki tabloda, rol ve framework'ün rol OLE bağlama ve katıştırma uygulamaları oluştururken gösterir. Bunlar gerçekleştirmek için seçenekleri yerine bir dizi adımın temsil eder.  
  
### <a name="creating-ole-applications"></a>OLE uygulamaları oluşturma  
  
|Görev|Bunu|Framework mu|  
|----------|------------|------------------------|  
|Bir COM bileşeni oluşturma.|MFC Uygulama Sihirbazı'nı çalıştırın. Seçin **tam sunucu** veya **Mini sunucu** içinde **bileşik belge desteği** sekmesi.|Framework etkin COM bileşeni özelliğine sahip bir iskelet uygulama oluşturur. Tüm COM yeteneğinin mevcut uygulamanıza yalnızca küçük değişiklik aktarılabilir.|  
|Bir kapsayıcı uygulamayı sıfırdan oluşturma.|MFC Uygulama Sihirbazı'nı çalıştırın. Seçin **kapsayıcı** içinde **bileşik belge desteği** sekmesi. Sınıf görünümü kullanarak, kaynak kodu Düzenleyici'ye gidin. COM işleyici işlevleri kodunu doldurun.|Framework COM bileşeni (sunucu) uygulamaları tarafından oluşturulan COM nesnelerini ekleyebilirsiniz iskelet bir uygulama oluşturur.|  
|Sıfırdan Automation'ı destekleyen bir uygulama oluşturun.|MFC Uygulama Sihirbazı'nı çalıştırın. Seçin **Otomasyon** gelen **Gelişmiş Özellikler** sekmesi. Sınıf Görünümü yöntemleri ve özellikleri Otomasyon için uygulamanızda kullanıma sunmak için kullanın.|Framework etkinleştirildi ve diğer uygulamalar tarafından otomatik iskelet bir uygulama oluşturur.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'te derleme](../mfc/building-on-the-framework.md)   
 [MFC uygulamaları oluşturmak için işlem dizisi](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [ActiveX denetimleri oluşturmak için işlem dizisi](../mfc/sequence-of-operations-for-creating-activex-controls.md)   
 [Veritabanı Uygulamaları Oluşturmak için İşlem Dizisi](../mfc/sequence-of-operations-for-creating-database-applications.md)

