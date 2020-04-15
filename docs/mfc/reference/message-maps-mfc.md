---
title: İleti Eşlemeleri (MFC)
ms.date: 09/07/2019
helpviewer_keywords:
- message maps [MFC], MFC
- Windows messages [MFC], message maps
- messages [MFC], Windows
- MFC, messages
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
ms.openlocfilehash: 8080becf1a1a153322bfd03cbd7006eaf2ce4e13
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356571"
---
# <a name="message-maps-mfc"></a>İleti Eşlemeleri (MFC)

Başvurunun bu bölümü, ilgili üye işlev prototipleriyle birlikte tüm [ileti eşleme makrolarını](../../mfc/reference/message-map-macros-mfc.md) ve tüm [CWnd](../../mfc/reference/cwnd-class.md) ileti eşleme girişlerini listeler:

|Kategori|Açıklama|
|--------------|-----------------|
|AİLE\_KOMUTU İleti Işleyicisi|Kullanıcı `WM_COMMAND` menüsü seçimleri veya menü erişim anahtarları tarafından oluşturulan iletileri işler.|
|[Alt Pencere Bildirim İletiSi İşleyicileri](../../mfc/reference/child-window-notification-message-handlers.md)|Alt pencerelerden gelen bildirim iletilerini işleyin.|
|[WM_ İleti Işleyicileri](../../mfc/reference/handlers-for-wm-messages.md)|İletileri `WM_` işle, `WM_PAINT`örneğin.|
|[Kullanıcı Tanımlı İleti Işleyicileri](../../mfc/reference/user-defined-handlers.md)|Kullanıcı tanımlı iletileri işleyebilir.|

(Bu başvuruda kullanılan terminoloji ve konvansiyonların açıklaması [için, Bkz. İleti Haritası Çapraz Başvuru Nasıl Kullanılır](../../mfc/reference/how-to-use-the-message-map-cross-reference.md)?)

Windows ileti tabanlı bir işletim sistemi olduğundan, Windows ortamı için programlamanın büyük bir bölümü ileti işlemeyi içerir. Tuş vuruşu veya fare tıklaması gibi bir olay her gerçekleştiğinde, uygulamaya bir ileti gönderilir ve bu da olayı işlemesi gerekir.

Microsoft Hazırlık Sınıf Kitaplığı, ileti tabanlı programlama için en iyi duruma getirilmiş bir programlama modeli sunar. Bu modelde, "ileti eşlemleri" belirli bir sınıf için çeşitli iletileri işleyeceğini belirlemek için kullanılır. İleti eşlemleri, hangi iletilerin hangi işlevler tarafından işleneceğini belirten bir veya daha fazla makro içerir. Örneğin, makro içeren bir `ON_COMMAND` ileti haritası aşağıdaki gibi görünebilir:

[!code-cpp[NVC_MFCMessageMaps#16](../../mfc/reference/codesnippet/cpp/message-maps-mfc_1.cpp)]

Makro, `ON_COMMAND` menüler, düğmeler ve hızlandırıcı tuşları tarafından oluşturulan komut iletilerini işlemek için kullanılır. [Makrolar](../../mfc/reference/message-map-macros-mfc.md) aşağıdakileri haritalamak için kullanılabilir:

## <a name="windows-messages"></a>Windows İletileri

- Denetim bildirimleri

- Kullanıcı tanımlı iletiler

## <a name="command-messages"></a>Komut Mesajları

- Kayıtlı kullanıcı tanımlı iletiler

- Kullanıcı arabirimi güncelleştirme iletileri

## <a name="ranges-of-messages"></a>İleti Aralıkları

- Komutlar

- Işleyici iletilerini güncelleştirme

- Denetim bildirimleri

İleti eşlemi makroları önemli olsa da, genellikle bunları doğrudan kullanmanız gerekmez. Bunun nedeni, [Sınıf Sihirbazı'nı](mfc-class-wizard.md) ileti işleme işlevlerini iletilerle ilişkilendirmek için kullandığınızda kaynak dosyalarınızda otomatik olarak ileti eşlemi girişleri oluşturmasıdır. Bir ileti eşlemi girişini ne zaman bir şekilde yapmak veya eklemek istediğinizde Sınıf Sihirbazı'nı kullanabilirsiniz.

> [!NOTE]
> Sınıf Sihirbazı ileti eşlemi aralıklarını desteklemez. Bu ileti eşlemi girişlerini kendiniz yazmalısınız.

Ancak, ileti eşlemleri Microsoft Hazırlık Sınıfı Kitaplığı'nın önemli bir parçasıdır. Ne yaptıklarını anlamalısınız ve onlar için belgeler sağlanmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Aramalar ve İleti Haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
