---
title: OLE uygulamaları oluşturmak için işlem dizisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE applications [MFC], creating
- OLE applications [MFC]
- applications [OLE], creating
- applications [OLE]
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 412fa5c104d6e85bcaa6ba3703cc8c7ba535f25f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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

