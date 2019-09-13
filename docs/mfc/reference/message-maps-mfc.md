---
title: İleti Eşlemeleri (MFC)
ms.date: 09/07/2019
helpviewer_keywords:
- message maps [MFC], MFC
- Windows messages [MFC], message maps
- messages [MFC], Windows
- MFC, messages
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
ms.openlocfilehash: 4305d9b1db297eebcb189d2fad98b8c634ed1133
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908035"
---
# <a name="message-maps-mfc"></a>İleti Eşlemeleri (MFC)

Başvurunun bu bölümünde, ilgili üye işlev prototipleriyle birlikte tüm [ileti eşleme makroları](../../mfc/reference/message-map-macros-mfc.md) ve tüm [CWnd](../../mfc/reference/cwnd-class.md) ileti eşleme girdileri listelenir:

|Kategori|Açıklama|
|--------------|-----------------|
|\_Komut iletisi işleyicisinde|Kullanıcı `WM_COMMAND` menü seçimleri veya menü erişim tuşları tarafından oluşturulan iletileri işler.|
|[Alt Pencere Bildirim İletisi İşleyicileri](../../mfc/reference/child-window-notification-message-handlers.md)|Alt pencerelerin bildirim iletilerini işleyin.|
|[WM_ Ileti Işleyicileri](../../mfc/reference/handlers-for-wm-messages.md)|Gibi `WM_` iletileri`WM_PAINT`işleyin.|
|[Kullanıcı tanımlı Ileti Işleyicileri](../../mfc/reference/user-defined-handlers.md)|Kullanıcı tanımlı iletileri işleyin.|

(Bu başvuruda kullanılan terminoloji ve kurallara ilişkin bir açıklama için bkz. [Ileti Haritası çapraz başvurusunu kullanma](../../mfc/reference/how-to-use-the-message-map-cross-reference.md).)

Windows, ileti yönelimli bir işletim sistemi olduğundan, Windows ortamı için programlama için büyük bir bölüm ileti işlemeyi içerir. Bir tuş vuruşu veya fare tıklaması gibi bir olay gerçekleştiğinde, uygulamaya bir ileti gönderilir ve bu daha sonra olayı ele almalıdır.

Microsoft Foundation Class Kitaplığı ileti tabanlı programlama için iyileştirilmiş bir programlama modeli sunar. Bu modelde, "ileti haritaları", belirli bir sınıf için çeşitli iletileri işleyeceği işlevleri belirlemek için kullanılır. İleti haritaları, hangi iletilerin hangi işlevleri tarafından işleneceğini belirten bir veya daha fazla makro içerir. Örneğin, bir `ON_COMMAND` makro içeren bir ileti haritası şuna benzeyebilir:

[!code-cpp[NVC_MFCMessageMaps#16](../../mfc/reference/codesnippet/cpp/message-maps-mfc_1.cpp)]

`ON_COMMAND` Makro, menüler, düğmeler ve hızlandırıcı tuşları tarafından oluşturulan komut iletilerini işlemek için kullanılır. [Makrolar](../../mfc/reference/message-map-macros-mfc.md) şu eşleme için kullanılabilir:

## <a name="windows-messages"></a>Windows Iletileri

- Denetim bildirimleri

- Kullanıcı tanımlı iletiler

## <a name="command-messages"></a>Komut Iletileri

- Kayıtlı Kullanıcı tanımlı iletiler

- Kullanıcı arabirimi güncelleştirme iletileri

## <a name="ranges-of-messages"></a>Ileti aralıkları

- Komutlar

- İşleyici iletilerini Güncelleştir

- Denetim bildirimleri

İleti eşleme makroları önemli olsa da, genellikle bunları doğrudan kullanmanız gerekmez. Bunun nedeni, [sınıf sihirbazının](mfc-class-wizard.md) ileti işleme işlevlerini iletilerle ilişkilendirmek için kullandığınızda, kaynak dosyalarınızda otomatik olarak ileti eşleme girdileri oluşturmasıdır. Herhangi bir ileti eşleme girişi düzenlemek veya eklemek istediğiniz zaman, sınıf sihirbazını kullanabilirsiniz.

> [!NOTE]
>  Sınıf Sihirbazı ileti eşleme aralıklarını desteklemez. Bu ileti eşleme girdilerini kendiniz yazmanız gerekir.

Ancak, ileti haritaları Microsoft Foundation Class Kitaplığı önemli bir bölümüdür. Ne yaptığını ve bunlar için belge sağlandığını anlamalısınız.

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
