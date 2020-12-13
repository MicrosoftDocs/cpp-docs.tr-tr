---
description: 'Hakkında daha fazla bilgi edinin: olay Işleme arabirimini uygulama'
title: Olay Işleme arabirimini uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, event handling
- event handling, ATL
- interfaces, event and event sink
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
ms.openlocfilehash: 109fbb1fbdd4f18d0eb4c295fbc08de2b7cc3a35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152769"
---
# <a name="implementing-the-event-handling-interface"></a>Olay Işleme arabirimini uygulama

ATL, olayları işlemek için gerekli olan üç öğe için size yardımcı olur: olay arabirimini uygulama, olay kaynağını Temizleme ve olay kaynağını geri alma. Gerçekleştirmeniz gereken kesin adımlar, olay arabiriminin türüne ve uygulamanızın performans gereksinimlerine göre değişir.

ATL kullanarak arabirim kullanmanın en yaygın yolları şunlardır:

- Özel arabirimden doğrudan türetiliyor.

- Bir tür kitaplığında açıklanan çift arabirimler için [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 'den türetiliyor.

- Bir tür kitaplığında açıklanan dispınterfaces için [IDispEventImpl](../atl/reference/idispeventimpl-class.md) öğesinden türetme.

- Bir tür kitaplığında açıklanmayan, görüntüleme arabirimleri için [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) 'den türetiliyor veya çalışma zamanında tür bilgilerini yüklemeerek verimliliği artırmak istediğinizde.

Özel veya çift bir arabirim uyguıyorsanız, [AtlAdvise](reference/connection-point-global-functions.md#atladvise) veya [CComPtrBase:: Advise](../atl/reference/ccomptrbase-class.md#advise)öğesini çağırarak olay kaynağına göre öneri almalısınız. Çağrı tarafından döndürülen tanımlama bilgisini takip etmeniz gerekir. Bağlantıyı kesmek için [AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise) çağrısı yapın.

Veya kullanarak bir dispınterface uyguıyorsanız `IDispEventImpl` `IDispEventSimpleImpl` , [IDispEventSimpleImpl::D Ispeventadmeni](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)çağırarak olay kaynağını önermelisiniz. Bağlantıyı kesmek için [IDispEventSimpleImpl::D ıspeventunadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise) öğesini çağırın.

`IDispEventImpl`Bileşik bir denetimin temel sınıfı olarak kullanıyorsanız, havuz eşlemesinde listelenen olay kaynakları, [CComCompositeControl:: Advisesınkmap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)kullanılarak otomatik olarak önerilir ve tavsiye edilir.

`IDispEventImpl`Ve `IDispEventSimpleImpl` sınıfları tanımlama bilgisini sizin için yönetir.

## <a name="see-also"></a>Ayrıca bkz.

[Olay Işleme](../atl/event-handling-and-atl.md)
