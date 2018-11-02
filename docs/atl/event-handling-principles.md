---
title: Olay işleme ilkeleri (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
ms.openlocfilehash: e460685d17a568d9e3b49af40dd1e3f1dbda7c28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610996"
---
# <a name="event-handling-principles"></a>Olay işleme ilkeleri

Tüm olay işleme için ortak üç adım vardır. Gerekir:

- Nesneniz üzerinde olay arabirimini uygulayın.

- Olay kaynağı, nesnenizin olayları almak istediğini önerin.

- Olay kaynağı, nesnenizin artık olayları almaya gerektiğinde eşlemesindeki.

Olay arabirimi uygulayacaksınız şekilde kendi türüne bağlıdır. Olay arabirimi vtable, dual veya dispinterface bir olabilir. Bu arabirim tanımlamak için tasarımcıya olay kaynağının kalmıştır; Bu, arabirim uygulamak için size aittir.

> [!NOTE]
>  Olay arabirimi çift olamaz hiçbir teknik nedenlerle olsa da, birkaç duals kullanımını önlemek için iyi bir tasarım nedenleri vardır. Ancak, bu olay Tasarımcısı/uygulayan tarafından yapılan bir karardır *kaynak*. Olay perspektifinden çalıştığınız beri `sink`, herhangi bir seçim olmayabilir olasılığı için izin vermek için ancak bir olayı çift arabirim uygulamak için gerekir. Çift arabirimler hakkında daha fazla bilgi için bkz. [çift arabirimler ve ATL](../atl/dual-interfaces-and-atl.md).

Olay kaynağı bildiren üç adımlamayla ayrılabilir:

- Kaynak nesne için sorgu [IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer).

- Çağrı [IConnectionPointContainer::FindConnectionPoint](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) arabirimi olay Laboratuvardaki geçirmeden, ilgilendiğiniz. Başarılı olursa bu döndürür, [IConnectionPoint](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint) arabirimdeki bir bağlantı noktası nesnesi.

- Çağrı [IConnectionPoint::Advise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-advise) geçirme `IUnknown` , olay havuzu. Başarılı olursa bu döndürür, bir `DWORD` bağlantıyı temsil eden bir tanımlama bilgisi.

Olaylarını alma konusundaki İlginiz başarıyla kaydettikten sonra kaynak nesnesi tarafından harekete geçirilen olayları göre nesnenizin olay arabirimdeki yöntemleri çağrılmaz. Artık olayları almaya ihtiyacınız olduğunda, bağlantı noktası dön tanımlama bilgisi geçirebilirsiniz [IConnectionPoint::Unadvise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-unadvise). Bu, kaynak ve havuz arasındaki bağlantıyı keser.

Başvuru kaçınmak için dikkatli olun olayları işlerken geçiş yapar.

## <a name="see-also"></a>Ayrıca Bkz.

[Olay İşleme](../atl/event-handling-and-atl.md)

