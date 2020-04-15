---
title: Olay İşleme İlkeleri (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
ms.openlocfilehash: 2e810853e7c81f279039e0b3dfda5199d38deee2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319575"
---
# <a name="event-handling-principles"></a>Olay Taşıma İlkeleri

Tüm olay işleme için ortak üç adım vardır. Şunları yapmanız gerekir:

- Nesnenizde olay arabirimini uygulayın.

- Nesnenizin olayları almak istediğini olay kaynağına bildirin.

- Nesnenizin artık olayları alması gerekmediğinde olay kaynağına bildirin.

Olay arabirimini uygulama şekliniz türüne bağlıdır. Olay arabirimi vtable, çift veya dispinterface olabilir. Bu arabirimi tanımlamak için olay kaynağının tasarımcısı kalmış; bu arayüzü uygulamak size kalmış.

> [!NOTE]
> Olay arabiriminin çift olmamasının teknik bir nedeni olmamasına rağmen, çift kullanımından kaçınmak için bir dizi iyi tasarım nedeni vardır. Ancak, bu olay *kaynağının*tasarımcısı / uygulayıcısı tarafından yapılan bir karardır. Olayın `sink`perspektifinden çalıştığından, çift olay arabirimi uygulamaktan başka seçeneğiniz olmayabilir olasılığına izin verebilirsiniz. Çift arayüzler hakkında daha fazla bilgi [için, Bkz. Çift Arayüzler ve ATL.](../atl/dual-interfaces-and-atl.md)

Olay kaynağının tavsiye edilmesi üç adıma ayrılabilir:

- [IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)için kaynak nesneyi sorgulayın.

- [IConnectionPointContainer'ı arayın::Sizi](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) ilgilendiren olay arabiriminin IID'sini geçen FindConnectionPoint. Başarılı olursa, bu bir bağlantı noktası nesnesi üzerinde [IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint) arabirimi döndürecek.

- [Çağrı IConnectionPoint::Olay](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise) `IUnknown` lavabo geçen tavsiye. Başarılı olursa, bu `DWORD` bağlantıyı temsil eden bir çerez döndürecek.

Olayları alma konusundaki ilginizi başarıyla kaydettirdikten sonra, nesnenizin olay arabirimindeki yöntemler kaynak nesne tarafından çalıştırılan olaylara göre çağrılacaktır. Artık etkinlik almanıza gerek kalmadığında, tanımlama bilgisini IConnectionPoint üzerinden bağlantı noktasına geri [geçirebilirsiniz::Unadvise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise). Bu, kaynak ve lavabo arasındaki bağlantıyı koparacaktır.

Olayları işlerken başvuru döngülerinden kaçınmaya dikkat edin.

## <a name="see-also"></a>Ayrıca bkz.

[Olay Yönetimi](../atl/event-handling-and-atl.md)
