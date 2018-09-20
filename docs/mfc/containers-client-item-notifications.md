---
title: 'Kapsayıcılar: İstemci öğesi bildirimleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], container client item
- OLE containers [MFC], client-item notifications
- client items and OLE containers
ms.assetid: e1f1c427-01f5-45f2-b496-c5bce3d76340
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5db5170b6c946e4bfeda99a3275f045a07fc9beb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435226"
---
# <a name="containers-client-item-notifications"></a>Kapsayıcılar: İstemci Öğesi Bildirimleri

Bu makalede, sunucu uygulamaları, istemci uygulamanızın belgedeki öğelerini değiştirdiğinizde, MFC çerçevesi çağıran geçersiz kılınabilir işlevler açıklanmaktadır.

[Coleclientıtem](../mfc/reference/coleclientitem-class.md) sunucu uygulaması olarak da bilinir bileşeni uygulamadan gelen isteklere yanıt olarak adlandırılan birden fazla geçersiz kılınabilir işlevler tanımlar. Bu geçersiz kılınabilen öğelerle ilgili genellikle bildirimleri olarak davranır. Bunlar, kaydırma, etkinleştirme gibi çeşitli olayları ya da bir değişiklik konumu ve düzenlerken veya aksi halde öğe düzenleme kullanıcının yaptığı değişiklikleri kapsayıcı uygulaması bildirin.

Kapsayıcı uygulamanızı değişiklik yapılan bir çağrıyla framework bildirir `COleClientItem::OnChange`, bir geçersiz kılınabilir işlevi uygulaması gereklidir. Bu korumalı işlevi iki bağımsız değişken alır. İlk öğe değiştirdik nedeni belirtir:

|Bildirim|Açıklama|
|------------------|-------------|
|**OLE_CHANGED**|OLE öğesinin görünümünü değişti.|
|**OLE_SAVED**|OLE öğesini kaydedildi.|
|**OLE_CLOSED**|OLE öğesini kapatıldı.|
|**OLE_RENAMED**|OLE öğesini içeren sunucu belgeyi yeniden adlandırıldı.|
|**OLE_CHANGED_STATE**|OLE öğesini bir durumdan diğerine değişti.|
|**OLE_CHANGED_ASPECT**|OLE öğesinin çizim en boy framework tarafından değiştirildi.|

Bu değerleri arasındadır **OLE_NOTIFICATION** AFXOLE içinde tanımlanan sabit listesi. H

Bu işlevin ikinci bağımsız değişkeni, öğe nasıl değiştiğini veya ne geçtiğinde tüketilen durum belirtir:

|İlk bağımsız değişken olduğunda|İkinci bağımsız değişkeni|
|----------------------------|---------------------|
|**OLE_SAVED** veya **OLE_CLOSED**|Kullanılmaz.|
|**OLE_CHANGED**|OLE öğesinin değişmiş en boy belirtir.|
|**OLE_CHANGED_STATE**|Girilen durumunu açıklar (*emptyState*, *loadedState*, *openState*, *activeState*, veya  *activeUIState*).|

İstemci öğesi varsayabilirsiniz durumları hakkında daha fazla bilgi için bkz. [kapsayıcılar: istemci öğesi durumları](../mfc/containers-client-item-states.md).

Framework çağrıları `COleClientItem::OnGetItemPosition` ne zaman bir öğe etkinleştirilmekte yerinde düzenleme için. Uygulama, yerinde düzenleme destekleyen uygulamalar için gereklidir. MFC Uygulama Sihirbazı öğenin koordinatlarına atar temel uygulamaları sağlar `CRect` bağımsız değişken olarak geçirilen nesne `OnGetItemPosition`.

Bir OLE öğesinin konumunu veya boyutu yerinde düzenleme sırasında değişirse, öğenin konumunu ve kırpma dikdörtgenler hakkında kapsayıcının bilgilerinin güncelleştirilmesi ve sunucu değişiklikleri konusunda bilgi alması gerekir. Framework çağrıları `COleClientItem::OnChangeItemPosition` bu amaç için. MFC Uygulama Sihirbazı, temel sınıfın işlevi çağıran bir geçersiz kılma sağlar. Uygulama Sihirbazı için yazar işlevi düzenlemeniz gerekir, `COleClientItem`-işlevi, istemci öğesi nesne tarafından tutulan herhangi bir bilgi güncelleştirilebilmesi için türetilmiş sınıf.

## <a name="see-also"></a>Ayrıca Bkz.

[Kapsayıcılar](../mfc/containers.md)<br/>
[Kapsayıcılar: İstemci Öğesi Durumları](../mfc/containers-client-item-states.md)<br/>
[COleClientItem::OnChangeItemPosition](../mfc/reference/coleclientitem-class.md#onchangeitemposition)

