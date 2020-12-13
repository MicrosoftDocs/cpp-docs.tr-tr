---
description: 'Daha fazla bilgi edinin: olay Işleme Ilkeleri'
title: Olay Işleme Ilkeleri (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
ms.openlocfilehash: 29b9542b4e026d320857990a0ef6253f310535e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147985"
---
# <a name="event-handling-principles"></a>Olay Işleme Ilkeleri

Tüm olay işleme için yaygın olarak kullanılan üç adım vardır. Şunları yapmanız gerekir:

- Nesneniz üzerinde olay arabirimini uygulayın.

- Olay kaynağını, nesnenizin olayları almak istediğini tavsiye edin.

- Nesnenizin artık olayları alması gerekmiyorsa olay kaynağını geri alın.

Olay arabirimini uygulama yöntemi, türüne bağlıdır. Olay Arabirimi vtable, Dual veya bir dispınterface olabilir. Bu, arabirimi tanımlamak için olay kaynağının tasarımcısına kadar olur; Bu arabirim sizin için uygulanır.

> [!NOTE]
> Bir olay arabiriminin çift olamaz gibi bir teknik neden olmasa da, duals kullanmaktan kaçınmak için bazı iyi tasarım nedenleri vardır. Ancak bu, olay *kaynağının* tasarımcı/uygulayıcısı tarafından yapılan bir karardır. Olayın perspektifinden çalıştığınızdan `sink` , herhangi bir seçeneğe sahip olmayabilirsiniz ancak ikili bir olay arabirimini uygulamak için izin vermeniz gerekir. Çift arabirimler hakkında daha fazla bilgi için bkz. [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md).

Olay kaynağının önerisi üç adımdan ayrılabilir:

- [IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)için kaynak nesnesini sorgulayın.

- Sizi ilgilendiren olay arabiriminin IID 'sini geçirerek [ınewctionpointcontainer:: FindConnectionPoint](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) çağırın. Bu işlem başarılı olursa, bir bağlantı noktası nesnesine [IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint) arabirimini döndürür.

- Olay havuzunu geçirerek [ınewctionpoint:: Advise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise) öğesini çağırın `IUnknown` . Bu işlem başarılı olursa, `DWORD` bağlantıyı temsil eden bir tanımlama bilgisi döndürür.

Olayları alma hakkında sizi başarıyla kaydettikten sonra, nesnenizin olay arabirimindeki Yöntemler, kaynak nesne tarafından tetiklenen olaylara göre çağrılır. Artık olay almanız gerekmiyorsa, bu tanımlama bilgisini [IConnectionPoint:: Unadvise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise)aracılığıyla bağlantı noktasına geri geçirebilirsiniz. Bu, kaynak ve havuz arasındaki bağlantıyı keser.

Olayları işlerken başvuru döngülerinden kaçınmak için dikkatli olun.

## <a name="see-also"></a>Ayrıca bkz.

[Olay Işleme](../atl/event-handling-and-atl.md)
