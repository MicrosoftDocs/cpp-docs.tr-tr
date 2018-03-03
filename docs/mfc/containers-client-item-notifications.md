---
title: "Kapsayıcılar: İstemci öğesi bildirimleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], container client item
- OLE containers [MFC], client-item notifications
- client items and OLE containers
ms.assetid: e1f1c427-01f5-45f2-b496-c5bce3d76340
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 58f995893f580ef41c27653a30e94d1f106fceb1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="containers-client-item-notifications"></a>Kapsayıcılar: İstemci Öğesi Bildirimleri
Bu makalede, sunucu uygulamaları istemci uygulamanızın belge öğelerini değiştirdiğinizde, MFC çerçevesi çağıran geçersiz kılınabilir işlevler açıklanmaktadır.  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md) sunucu uygulaması olarak da bilinir bileşen uygulamasından isteklerine yanıt olarak adlandırılan birden fazla geçersiz kılınabilir işlevler tanımlar. Bu geçersiz kılınabilir genellikle bildirimleri olarak davranır. Bunlar, kaydırma, etkinleştirme gibi çeşitli olayları veya bir değişiklik konumunu ve kullanıcı düzenlerken veya aksi halde öğesi düzenleme yaptığı değişiklikler kapsayıcı uygulamasının bildirin.  
  
 Kapsayıcı uygulamanızı çağrısıyla değişiklikleri framework bildirir `COleClientItem::OnChange`, geçersiz kılınabilir bir işlevi olan uygulaması gereklidir. Bu korumalı işlevi iki bağımsız değişkeni alır. İlk öğe sunucu değişti nedenini belirtir:  
  
|Bildirim|Açıklama|  
|------------------|-------------|  
|`OLE_CHANGED`|OLE öğesi'nin görünümü değiştirilmiştir.|  
|`OLE_SAVED`|OLE öğesi kaydedildi.|  
|`OLE_CLOSED`|OLE öğesi kapatıldı.|  
|**OLE_RENAMED**|OLE öğesi içeren sunucu belgeyi yeniden adlandırıldı.|  
|`OLE_CHANGED_STATE`|OLE öğesi bir durumdan diğerine değişti.|  
|**OLE_CHANGED_ASPECT**|OLE öğesi'nin çizim en boy çerçevesi tarafından değiştirildi.|  
  
 Bu değerleri arasındadır **OLE_NOTIFICATION** AFXOLE içinde tanımlanan numaralandırması. H.  
  
 Bu işlevin ikinci bağımsız değişken öğe nasıl değiştiğini veya ne girilen durum belirtir:  
  
|İlk bağımsız değişken olduğunda|İkinci bağımsız değişken|  
|----------------------------|---------------------|  
|`OLE_SAVED`veya`OLE_CLOSED`|Kullanılmaz.|  
|`OLE_CHANGED`|Değişti OLE öğesi yönünü belirtir.|  
|`OLE_CHANGED_STATE`|Girilen durumu açıklar (`emptyState`, **loadedState**, `openState`, `activeState`, veya `activeUIState`).|  
  
 Bir istemci öğesi varsayabilirsiniz durumları hakkında daha fazla bilgi için bkz: [kapsayıcılar: istemci öğesi durumları](../mfc/containers-client-item-states.md).  
  
 Framework çağrıları `COleClientItem::OnGetItemPosition` ne zaman bir öğe etkinleştiriliyor yerinde düzenleme için. Uygulama yerinde düzenleme destekleyen uygulamalar için gereklidir. MFC Uygulama Sihirbazı'nı öğesi'nin koordinatlara atar temel bir uygulama sağlar `CRect` bağımsız değişken olarak geçirilen nesne `OnGetItemPosition`.  
  
 OLE öğenin konum veya boyut yerinde düzenleme sırasında değişirse, kapsayıcının bilgilerini öğesi'nin konumu ve kırpma dikdörtgenler güncelleştirilmesi gerekir ve sunucu değişiklikler hakkında bilgi alması gerekir. Framework çağrıları `COleClientItem::OnChangeItemPosition` bu amaç için. MFC Uygulama Sihirbazı'nı temel sınıfın işlevi çağıran bir geçersiz kılma sağlar. İçin Uygulama Sihirbazı'nı Yazar işlevi düzenlemeniz gerekir, `COleClientItem`-işlevi istemci öğesi nesnesi tarafından korunduğunu herhangi bir bilgi güncelleştirilebilmesi için türetilmiş sınıf.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kapsayıcıları](../mfc/containers.md)   
 [Kapsayıcılar: İstemci öğesi durumları](../mfc/containers-client-item-states.md)   
 [COleClientItem::OnChangeItemPosition](../mfc/reference/coleclientitem-class.md#onchangeitemposition)

