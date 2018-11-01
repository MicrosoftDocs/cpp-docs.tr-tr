---
title: Görünümleri Kaydırma ve Ölçeklendirme
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [MFC]
- scaling views [MFC]
- message handling [MFC], scroll bars in view class [MFC]
- scroll bars [MFC], messages
- scrolling views [MFC]
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
ms.openlocfilehash: acef79a89da88773da564fc965a607e2fd5b53f7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626123"
---
# <a name="scrolling-and-scaling-views"></a>Görünümleri Kaydırma ve Ölçeklendirme

MFC bunları görüntüler çerçeve penceresinin boyutunu otomatik olarak ölçeklendirilen kaydırın ve görünümleri görünümleri destekler. Sınıf `CScrollView` görünümleri her iki tür destekler.

Kaydırma ve ölçeklendirme hakkında daha fazla bilgi için bkz. [CScrollView](../mfc/reference/cscrollview-class.md) içinde *MFC başvurusu*. Kayan bir örnek için bkz: [Scribble örneğinin](../visual-cpp-samples.md).

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- Bir görünüm kaydırma

- Bir görünüm ölçeklendirme

- [Görünüm koordinatları](/windows/desktop/gdi/window-coordinate-system)

##  <a name="_core_scrolling_a_view"></a> Bir görünüm kaydırma

Sık belgenin görünümünü görüntüleyebilirsiniz boyutundan büyük boyutudur. Bu belgenin verilerini artırır veya Görünüm çerçeve penceresi kullanıcı daraltır nedeniyle ortaya çıkabilir. Böyle durumlarda, kaydırma görünümü desteklemesi gerekir.

Herhangi bir görünüm, kaydırma çubuğu iletileri işleyebilir, `OnHScroll` ve `OnVScroll` üye işlevleri. Bu işlevlerin her iki uygulama kaydırma çubuğu ileti işleme tüm işini kendiniz yapmak için ya da kullanabilirsiniz `CScrollView` sizin için kaydırma işlemek için sınıf.

`CScrollView` şunları yapar:

- Pencere ve Görünüm penceresi boyutları ve eşleme modları yönetir

- Otomatik kaydırma çubuğu iletilere yanıt olarak kaydırır

Ne kadar "(kullanıcı bir kaydırma çubuğu mil tıkladığında) bir sayfası" ve "satır" için (kullanıcı bir kaydırma oka tıkladığında) kaydırmak için belirtebilirsiniz. Bu değerleri niteliği görünümünüzde uyacak şekilde planlayın. Örneğin, bir grafik görünümü için 1 piksel artırır ancak metin belgelerde satır yüksekliği göre halinde kaydırın isteyebilirsiniz.

##  <a name="_core_scaling_a_view"></a> Bir görünüm ölçeklendirme

Görünümü otomatik olarak alt çerçeve penceresi sığacak şekilde istediğiniz zaman kullanabileceğiniz `CScrollView` kaydırma yerine ölçeklendirme için. Mantıksal görünüm esnetildiğini veya pencerenin istemci alanını tam olarak sığması için küçültülebilir. Ölçeklendirilmiş bir görünüm, kaydırma çubukları vardır.

## <a name="see-also"></a>Ayrıca Bkz.

[Görünümleri Kullanma](../mfc/using-views.md)

