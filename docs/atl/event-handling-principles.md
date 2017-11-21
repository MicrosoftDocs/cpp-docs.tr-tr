---
title: "Olay işleme ilkeleri (ATL) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c37544f7b9083bbfa890961ef40e0c9f26aecc2c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="event-handling-principles"></a>Olay işleme ilkeleri
Tüm olay işleme ortak üç adım vardır. Gerekir:  
  
-   Olay arabirimini nesnenize uygulayın.  
  
-   Olay kaynağı nesnenizin olayları almak istediği öneriyoruz.  
  
-   Olay kaynağı nesnenizin olaylarını almak artık ihtiyaç duyduğunda unadvise.  
  
 Olay arabirimini uygulayan şekilde, kendi türüne bağlıdır. Bir olay arabirimi vtable, çift ya da bir görüntüleme arabirimi olabilir. Bu arabirimi tanımlamak için tasarımcısına olay kaynağı olan; Bu, bu arabirim uygulamak için hazır.  
  
> [!NOTE]
>  Bir olay arabirimi çift olamaz hiçbir teknik nedenlerle olsa da, pek çok duals kullanımını önlemek için iyi tasarım vardır. Ancak, bu olay Tasarımcısı/uygulayan tarafından yapılan bir karardır *kaynak*. Olay perspektifinden çalıştığınız beri `sink`, herhangi bir seçiminde olmayabilir olasılığı için izin vermek için ancak bir çift olay arabirimi uygulamak için gerekir. Çift arabirimler hakkında daha fazla bilgi için bkz: [çift arabirimler ve ATL](../atl/dual-interfaces-and-atl.md).  
  
 Olay kaynağı bildiren üç adımı ayrılabilir:  
  
-   Kaynak nesne için sorgu [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857).  
  
-   Çağrı [IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) olay arabirimini IID geçirme, ilgilendiğiniz. Başarılı, bu döndürür, [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318) bir bağlantı noktası nesnesindeki arabirim.  
  
-   Çağrı [IConnectionPoint::Advise](http://msdn.microsoft.com/library/windows/desktop/ms678815) geçirme **IUnknown** olay iç havuz. Başarılı, bu döndürür, bir `DWORD` bağlantıyı temsil eden tanımlama bilgisi.  
  
 Olayları alma ilginize başarıyla kaydettikten sonra nesnenin olay arabirim yöntemleri kaynak nesne tarafından tetiklenen olaylara göre çağrılır. Artık olaylarını almak gerektiğinde, bağlantı noktası dön tanımlama bilgisinin geçirebilirsiniz [IConnectionPoint::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608). Bu kaynak ve havuz arasındaki bağlantıyı çalışmamasına neden olur.  
  
 Başvuru kaçınmak için dikkatli olun olayları işlerken geçiş yapar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olay işleme](../atl/event-handling-and-atl.md)

