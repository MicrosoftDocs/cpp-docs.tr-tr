---
title: 'Kapsayıcılar: İstemci Öğesi Bildirimleri'
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], container client item
- OLE containers [MFC], client-item notifications
- client items and OLE containers
ms.assetid: e1f1c427-01f5-45f2-b496-c5bce3d76340
ms.openlocfilehash: 54b1b2a64685b00fb265e0f80c1f6ad878a7da85
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623011"
---
# <a name="containers-client-item-notifications"></a>Kapsayıcılar: İstemci Öğesi Bildirimleri

Bu makalede, sunucu uygulamaları istemci uygulamanızın belgesindeki öğeleri değiştirirken MFC çerçevesinin çağırdığı geçersiz kılınabilir işlevler açıklanır.

[Coleclientidıtem](reference/coleclientitem-class.md) , bileşen uygulamasından gelen isteklere yanıt olarak çağrılan ve sunucu uygulaması olarak da adlandırılan birkaç geçersiz kılınabilir işlevi tanımlar. Bu geçersiz kılınan kasalar genellikle bildirim olarak davranır. Kapsayıcı uygulamasını, kaydırma, etkinleştirme veya konum değişikliği gibi çeşitli olayların yanı sıra, öğeyi düzenleme veya başka bir şekilde düzenleme sırasında yaptığı değişikliklere göre bilgilendirir.

Çerçeve, bir çağrısı aracılığıyla kapsayıcı uygulamanızı `COleClientItem::OnChange` , uygulaması gerekli olan geçersiz kılınabilir bir işlev ile bilgilendirir. Bu korumalı işlev iki bağımsız değişken alır. Birincisi, sunucunun öğeyi değiştirme nedenini belirtir:

|Bildirim|Anlamı|
|------------------|-------------|
|**OLE_CHANGED**|OLE öğesinin görünümü değişti.|
|**OLE_SAVED**|OLE öğesi kaydedildi.|
|**OLE_CLOSED**|OLE öğesi kapatıldı.|
|**OLE_RENAMED**|OLE öğesini içeren sunucu belgesi yeniden adlandırıldı.|
|**OLE_CHANGED_STATE**|OLE öğesi bir durumdan diğerine değişti.|
|**OLE_CHANGED_ASPECT**|OLE öğesinin çizim yönü Framework tarafından değiştirildi.|

Bu değerler, AFXOLE ' de tanımlanan **OLE_NOTIFICATION** numaralandırmadır. Olsun.

Bu işlevin ikinci bağımsız değişkeni, öğenin nasıl değiştiğini veya ne durum girildiğini belirtir:

|İlk bağımsız değişken olduğunda|İkinci bağımsız değişken|
|----------------------------|---------------------|
|**OLE_SAVED** veya **OLE_CLOSED**|Kullanılmaz.|
|**OLE_CHANGED**|Değiştirilen OLE öğesinin yönünü belirtir.|
|**OLE_CHANGED_STATE**|Girilen durumu açıklar (*emptyState*, *loadedState*, *openState*, *ActiveState*veya *activeuistate*).|

Bir istemci öğesinin varsaydığı durumlar hakkında daha fazla bilgi için bkz. [kapsayıcılar: istemci-öğe durumları](containers-client-item-states.md).

Çerçeve, `COleClientItem::OnGetItemPosition` bir öğe yerinde düzenlenmek için etkinleştirildiğinde çağrılır. Uygulama, yerinde düzenlemeden desteklenen uygulamalar için gereklidir. MFC Uygulama Sihirbazı, öğenin koordinatlarını `CRect` öğesine bir bağımsız değişken olarak geçirilen nesneye atayan temel bir uygulama sağlar `OnGetItemPosition` .

Bir OLE öğesinin konumu veya boyutu yerinde düzenlemede değişirse, kapsayıcının öğenin konumu ve kırpma dikdörtgenleri hakkındaki bilgileri güncelleştirilmeleri ve sunucunun değişiklikler hakkında bilgi alması gerekir. Framework `COleClientItem::OnChangeItemPosition` Bu amaca yönelik çağrılar. MFC Uygulama Sihirbazı, temel sınıfın işlevini çağıran bir geçersiz kılma sağlar. `COleClientItem`İşlevin, istemci öğe nesneniz tarafından korunan tüm bilgileri güncelleştirmesi için, uygulama Sihirbazı 'nın türetilmiş sınıfınız için yazdığı işlevi düzenlemeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcılar](containers.md)<br/>
[Kapsayıcılar: İstemci Öğesi Durumları](containers-client-item-states.md)<br/>
[Colet Clientıtem:: OnChangeItemPosition](reference/coleclientitem-class.md#onchangeitemposition)
