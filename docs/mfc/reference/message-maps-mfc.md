---
title: İleti eşlemeleri (MFC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- message maps [MFC], MFC
- Windows messages [MFC], message maps
- messages [MFC], Windows
- MFC, messages
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e9d8953d637275ab44c43a58a15553f8e4284f84
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374255"
---
# <a name="message-maps-mfc"></a>İleti Eşlemeleri (MFC)

Başvurusunun bu bölümü listeler [ileti eşleme makroları](../../mfc/reference/message-map-macros-mfc.md) ve tüm [CWnd](../../mfc/reference/cwnd-class.md) ileti eşlemesi girişleri birlikte karşılık gelen üye işlev prototipleri:

|Kategori|Açıklama|
|--------------|-----------------|
|Açık\_komut ileti işleyicisi|İşleme `WM_COMMAND` kullanıcı menüsü seçeneklerini veya menü erişim anahtarları tarafından oluşturulan iletileri.|
|[Alt Pencere Bildirim İletisi İşleyicileri](../../mfc/reference/child-window-notification-message-handlers.md)|Alt öğe pencerelerini gelen bildirim iletileri işler.|
|[WM_ ileti işleyicileri](../../mfc/reference/handlers-for-wm-messages.md)|Tanıtıcı `WM_` gibi iletileri `WM_PAINT`.|
|[Kullanıcı tanımlı ileti işleyicileri](../../mfc/reference/user-defined-handlers.md)|Kullanıcı tanımlı iletileri işler.|

(Bu başvuruda kullanılan kuralları ve terminolojisi açıklaması için bkz. [ileti eşleme çapraz başvurusunu kullanma](../../mfc/reference/how-to-use-the-message-map-cross-reference.md).)

Windows, bir iletiye yönelik işletim sistemi olduğundan, Windows ortamınıza programming büyük bir kısmı ileti işleme içerir. Her oluştuğunda bir tuş vuruşu veya fare gibi bir olay'ı tıklatın, sonra olay işlemesi gerekir uygulama bir mesajı gönderilir.

Microsoft Foundation Class Kitaplığı, ileti tabanlı programlama için en iyi duruma getirilmiş bir programlama modeli sunar. Bu modelde, "haritalar message" hangi işlevleri çeşitli iletiler için belirli bir sınıfın işleyeceğini belirtmek için kullanılır. İleti eşlemeleri hangi işlevleri tarafından hangi iletilerin işleneceğini belirten bir veya daha fazla makrolar içerir. Örneğin, bir ileti eşleme içeren bir `ON_COMMAND` makrosu şöyle görünebilir:

[!code-cpp[NVC_MFCMessageMaps#16](../../mfc/reference/codesnippet/cpp/message-maps-mfc_1.cpp)]

`ON_COMMAND` Makrosu, menüler, düğmeler ve kısayol tuşları tarafından oluşturulan komut iletileri işlemek için kullanılır. [Makrolar](../../mfc/reference/message-map-macros-mfc.md) aşağıdaki eşlemek kullanılabilir:

## <a name="windows-messages"></a>Windows iletileri

- Denetim bildirimleri

- Kullanıcı tanımlı iletiler

## <a name="command-messages"></a>Komut iletileri

- Kayıtlı kullanıcı tanımlı iletiler

- Kullanıcı arabirimini güncelleştirme iletileri

## <a name="ranges-of-messages"></a>İleti aralıkları

- Komutlar

- Güncelleştirme işleyici iletileri

- Denetim bildirimleri

İleti eşleme makroları önemli olsa da, genellikle doğrudan kullanmanız gerekmez. İleti işleme işlevleri iletileri ile ilişkilendirilecek kullandığınızda Özellikler penceresi, kaynak dosyalarında ileti eşlemesi girişleri otomatik olarak oluşturur. olmasıdır. Düzenlemek veya bir ileti eşleme girdisi eklemek için istediğiniz zaman, Özellikler penceresini kullanabilirsiniz.

> [!NOTE]
>  Özellikler penceresinde ileti eşleme aralıkları desteklemez. Bu ileti eşlemesi girişleri kendiniz yazmalısınız.

Microsoft Foundation Class Kitaplığı, ileti eşlemeleri ancak önemli bir parçasıdır. Yaptıkları anlamanız gerekir ve belgeleri için sağlanır.

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

