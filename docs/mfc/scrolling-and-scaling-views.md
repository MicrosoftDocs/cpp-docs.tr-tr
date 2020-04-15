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
ms.openlocfilehash: 366f0e2953e5190f80a2877804bff2fc7dbbd520
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372783"
---
# <a name="scrolling-and-scaling-views"></a>Görünümleri Kaydırma ve Ölçeklendirme

MFC, kaydırış yapan görünümleri ve bunları görüntüleyen çerçeve penceresinin boyutuna otomatik olarak ölçeklendirilen görünümleri destekler. Sınıf `CScrollView` her iki tür de görünümü destekler.

Kaydırma ve ölçekleme hakkında daha fazla bilgi için *MFC Başvurusu'ndaki* [CScrollView](../mfc/reference/cscrollview-class.md) sınıfına bakın. Kaydırma örneği için Karalama [örneğine](../overview/visual-cpp-samples.md)bakın.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- Görünüm kaydırma

- Görünümü ölçekleme

- [Koordinatları görüntüleme](/windows/win32/gdi/window-coordinate-system)

## <a name="scrolling-a-view"></a><a name="_core_scrolling_a_view"></a>Görünüm kaydırma

Bir belgenin boyutu sık sık görünümün görüntülenebildiği boyuttan daha büyüktür. Bu, belgenin verilerini artırdığı veya kullanıcı görünümü çerçeveleyen pencereyi küçültttünden oluşabilir. Bu gibi durumlarda, görünüm kaydırmayı desteklemelidir.

Herhangi bir görünüm, kaydırma çubuğu `OnHScroll` iletilerini kendi ve `OnVScroll` üye işlevlerinde işleyebilir. Bu işlevlerde kaydırma çubuğu iletisi işlemeyi kendiniz yaparak uygulayabilir veya `CScrollView` sınıfı sizin için kaydırma işlemek için kullanabilirsiniz.

`CScrollView`aşağıdakileri yapar:

- Pencere ve görüntü noktası boyutlarını ve eşleme modlarını yönetir

- Kaydırma çubuğu iletilerine yanıt olarak otomatik olarak kaydırılır

Bir "sayfa" (kullanıcı kaydırma çubuğu şaftında tıkladığında) ve "satır" (kullanıcı kaydırma okuna tıkladığında) için ne kadar kaydırma yapılacağını belirtebilirsiniz. Bu değerleri, görüşünüzün doğasına uyacak şekilde planlayın. Örneğin, grafik görünümü için 1 piksellik artışlarla, ancak metin belgelerindeki satır yüksekliğine bağlı olarak artışlarla kaydırmak isteyebilirsiniz.

## <a name="scaling-a-view"></a><a name="_core_scaling_a_view"></a>Görünümü Ölçekleme

Görünümün çerçeve penceresinin boyutuna otomatik olarak sığmasını istediğinizde, kaydırma yerine ölçekleme için kullanabilirsiniz. `CScrollView` Mantıksal görünüm, pencerenin istemci alanına tam olarak uyacak şekilde uzatılır veya küçültülmüşdür. Ölçeklenmiş görünümün kaydırma çubuğu yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Görünümleri Kullanma](../mfc/using-views.md)
