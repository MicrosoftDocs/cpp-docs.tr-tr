---
description: 'Daha fazla bilgi için: Ileti haritaları (MFC)'
title: İleti Eşlemeleri (MFC)
ms.date: 09/07/2019
helpviewer_keywords:
- message maps [MFC], MFC
- Windows messages [MFC], message maps
- messages [MFC], Windows
- MFC, messages
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
ms.openlocfilehash: 7647104d62cbbf10271ddb9e7c781da0049985f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219362"
---
# <a name="message-maps-mfc"></a>İleti Eşlemeleri (MFC)

Başvurunun bu bölümünde, ilgili üye işlev prototipleriyle birlikte tüm [ileti eşleme makroları](../../mfc/reference/message-map-macros-mfc.md) ve tüm [CWnd](../../mfc/reference/cwnd-class.md) ileti eşleme girdileri listelenir:

|Kategori|Açıklama|
|--------------|-----------------|
|\_Komut Iletisi işleyicisinde|`WM_COMMAND`Kullanıcı menü seçimleri veya menü erişim tuşları tarafından oluşturulan iletileri işler.|
|[Alt pencere bildirim Iletisi Işleyicileri](../../mfc/reference/child-window-notification-message-handlers.md)|Alt pencerelerin bildirim iletilerini işleyin.|
|[WM_ Ileti Işleyicileri](../../mfc/reference/handlers-for-wm-messages.md)|Gibi `WM_` iletileri işleyin `WM_PAINT` .|
|[Kullanıcı tanımlı Ileti Işleyicileri](../../mfc/reference/user-defined-handlers.md)|Kullanıcı tanımlı iletileri işleyin.|

(Bu başvuruda kullanılan terminoloji ve kurallara ilişkin bir açıklama için bkz. [Ileti Haritası çapraz başvurusunu kullanma](../../mfc/reference/how-to-use-the-message-map-cross-reference.md).)

Windows, ileti yönelimli bir işletim sistemi olduğundan, Windows ortamı için programlama için büyük bir bölüm ileti işlemeyi içerir. Bir tuş vuruşu veya fare tıklaması gibi bir olay gerçekleştiğinde, uygulamaya bir ileti gönderilir ve bu daha sonra olayı ele almalıdır.

Microsoft Foundation Class Kitaplığı ileti tabanlı programlama için iyileştirilmiş bir programlama modeli sunar. Bu modelde, "ileti haritaları", belirli bir sınıf için çeşitli iletileri işleyeceği işlevleri belirlemek için kullanılır. İleti haritaları, hangi iletilerin hangi işlevleri tarafından işleneceğini belirten bir veya daha fazla makro içerir. Örneğin, bir makro içeren bir ileti haritası şuna benzeyebilir `ON_COMMAND` :

[!code-cpp[NVC_MFCMessageMaps#16](../../mfc/reference/codesnippet/cpp/message-maps-mfc_1.cpp)]

`ON_COMMAND`Makro, menüler, düğmeler ve hızlandırıcı tuşları tarafından oluşturulan komut iletilerini işlemek için kullanılır. [Makrolar](../../mfc/reference/message-map-macros-mfc.md) şu eşleme için kullanılabilir:

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
> Sınıf Sihirbazı ileti eşleme aralıklarını desteklemez. Bu ileti eşleme girdilerini kendiniz yazmanız gerekir.

Ancak, ileti haritaları Microsoft Foundation Class Kitaplığı önemli bir bölümüdür. Ne yaptığını ve bunlar için belge sağlandığını anlamalısınız.

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, stiller, geri çağrılar ve Ileti haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
