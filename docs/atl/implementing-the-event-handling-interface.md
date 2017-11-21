---
title: "Olay arabirimi işleme uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ATL, event handling
- event handling, ATL
- interfaces, event and event sink
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3ea192e863fe9813a762c0c948cc141b068c3f43
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="implementing-the-event-handling-interface"></a>Olay işleme arabirimi uygulama
ATL yardımcı olan olayları işlemek için gerekli tüm üç öğelerle: olay arabirimini uygulayan, olay kaynağı bildiren ve olay kaynağı unadvising. Almanız gerekecek kesin adımlar olay arabirimini ve uygulamanızın performansı gereksinimlerini türüne bağlıdır.  
  
 ATL kullanarak arabirimi uygulama en sık kullanılan yöntemler şunlardır:  
  
-   Özel bir arabiriminden doğrudan türetme.  
  
-   Türetme [IDispatchImpl](../atl/reference/idispatchimpl-class.md) bir tür kitaplığı'nda açıklanan çift arabirimler için.  
  
-   Türetme [IDispEventImpl](../atl/reference/idispeventimpl-class.md) bir tür kitaplığı'nda açıklanan dispinterfaces için.  
  
-   Türetme [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) bir tür kitaplığı veya çalışma zamanında tür bilgilerini yüklenmemesi verimliliğini artırmak istediğinizde açıklanmayan dispinterfaces için.  
  

 Bir özel veya çift arabirim uyguluyorsanız, olay kaynağı çağırarak tutumunuzu [AtlAdvise](reference/connection-point-global-functions.md#atladvise) veya [CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise). Kendiniz çağrı tarafından döndürülen tanımlama bilgisi izlemek gerekir. Çağrı [AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise) bağlantıyı kesmek için.  

  
 Görüntüleme arabirimi kullanarak uyguluyorsanız `IDispEventImpl` veya `IDispEventSimpleImpl`, olay kaynağı çağırarak tutumunuzu [IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise). Çağrı [IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise) bağlantıyı kesmek için.  
  
 Kullanıyorsanız `IDispEventImpl` bileşik denetim temel sınıf olarak havuz eşlemesinde listelenen olay kaynakları tavsiye edilir ve unadvised kullanılarak otomatik olarak olacaktır [CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).  
  
 `IDispEventImpl` Ve `IDispEventSimpleImpl` sınıfları sizin için tanımlama bilgisi yönetin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olay işleme](../atl/event-handling-and-atl.md)

