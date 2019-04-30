---
title: İleti Eşlemeleri (MFC)
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.messages
helpviewer_keywords:
- message maps [MFC], MFC
- Windows messages [MFC], message maps
- messages [MFC], Windows
- MFC, messages
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
ms.openlocfilehash: 91b7f21d92b2f899895b008b3fab8b541aec9963
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412793"
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

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
