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
ms.openlocfilehash: 7064880c5ceef8e7dc3e35bb7ef5bc700b0842d2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511222"
---
# <a name="scrolling-and-scaling-views"></a>Görünümleri Kaydırma ve Ölçeklendirme

MFC, kaydırılan ve görüntülenen görünümleri destekler ve bunları görüntüleyen çerçeve penceresinin boyutuna otomatik olarak ölçeklendirilir. Sınıf `CScrollView` her iki türde görünümü destekler.

Kaydırma ve ölçeklendirme hakkında daha fazla bilgi için *MFC başvurusu*Içindeki Class [CScrollView](../mfc/reference/cscrollview-class.md) bölümüne bakın. Kaydırılan bir örnek için bkz. [karalama örneği](../overview/visual-cpp-samples.md).

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- Bir görünüm kaydırma

- Görünümü ölçekleme

- [Koordinatları görüntüle](/windows/win32/gdi/window-coordinate-system)

##  <a name="_core_scrolling_a_view"></a>Bir görünüm kaydırma

Genellikle bir belgenin boyutu, görünümü tarafından görüntülenebilecek boyuttan daha büyük. Bu durum belge verilerinin arttığı veya kullanıcının görünümü çerçevelerin pencereyi küçülmesi nedeniyle ortaya çıkabilir. Bu gibi durumlarda, görünümün kaydırmayı desteklemesi gerekir.

Herhangi bir görünüm, `OnHScroll` ve `OnVScroll` üye işlevlerinde kaydırma çubuğu iletilerini işleyebilir. Bu işlevlerde kaydırma çubuğu ileti işleme uygulayabilir, tüm işleri kendiniz yapabilir veya kaydırma işlemini sizin için işlemek üzere kullanabilirsiniz `CScrollView` .

`CScrollView`şunları yapar:

- Pencere ve Görünüm penceresi boyutlarını ve eşleme modlarını yönetir

- Kaydırma çubuğu iletilerine yanıt olarak otomatik olarak kaydırır

"Sayfa" için ne kadar kaydırılacağını (Kullanıcı bir kaydırma çubuğu Shaft 'e tıkladığında) ve bir "satır" (Kullanıcı bir kaydırma okuna tıkladığı zaman) belirtebilirsiniz. Bu değerleri görünümlerinizin yapısına uyacak şekilde planlayın. Örneğin, bir grafik görünümü için 1 piksellik artışlarla, metin belgelerindeki çizgi yüksekliğine göre artışlarla kaydırmak isteyebilirsiniz.

##  <a name="_core_scaling_a_view"></a>Görünümü ölçekleme

Görünümün otomatik olarak çerçeve penceresinin boyutuna sığması istediğinizde, kaydırma yerine ölçekleme için kullanabilirsiniz `CScrollView` . Mantıksal Görünüm, pencerenin istemci alanına tam olarak sığması için uzatılır veya küçültülebilir. Ölçeklenen bir görünüm, kaydırma çubuklarına sahip değildir.

## <a name="see-also"></a>Ayrıca bkz.

[Görünümleri Kullanma](../mfc/using-views.md)
