---
description: 'Daha fazla bilgi edinin: görünümleri kaydırma ve ölçeklendirme'
title: Görünümleri Kaydırma ve Ölçeklendirme
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [MFC]
- scaling views [MFC]
- message handling [MFC], scroll bars in view class [MFC]
- scroll bars [MFC], messages
- scrolling views [MFC]
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
ms.openlocfilehash: f18b774eadf875f61fcb1f3f3a8dc9e0e370f9a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217815"
---
# <a name="scrolling-and-scaling-views"></a>Görünümleri Kaydırma ve Ölçeklendirme

MFC, kaydırılan ve görüntülenen görünümleri destekler ve bunları görüntüleyen çerçeve penceresinin boyutuna otomatik olarak ölçeklendirilir. Sınıf `CScrollView` her iki türde görünümü destekler.

Kaydırma ve ölçeklendirme hakkında daha fazla bilgi için *MFC başvurusu* Içindeki Class [CScrollView](../mfc/reference/cscrollview-class.md) bölümüne bakın. Kaydırılan bir örnek için bkz. [karalama örneği](../overview/visual-cpp-samples.md).

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- Bir görünüm kaydırma

- Görünümü ölçekleme

- [Koordinatları görüntüle](/windows/win32/gdi/window-coordinate-system)

## <a name="scrolling-a-view"></a><a name="_core_scrolling_a_view"></a> Bir görünüm kaydırma

Genellikle bir belgenin boyutu, görünümü tarafından görüntülenebilecek boyuttan daha büyük. Bu durum belge verilerinin arttığı veya kullanıcının görünümü çerçevelerin pencereyi küçülmesi nedeniyle ortaya çıkabilir. Bu gibi durumlarda, görünümün kaydırmayı desteklemesi gerekir.

Herhangi bir görünüm, `OnHScroll` ve üye işlevlerinde kaydırma çubuğu iletilerini işleyebilir `OnVScroll` . Bu işlevlerde kaydırma çubuğu ileti işleme uygulayabilir, tüm işleri kendiniz yapabilir veya `CScrollView` kaydırma işlemini sizin için işlemek üzere kullanabilirsiniz.

`CScrollView` şunları yapar:

- Pencere ve Görünüm penceresi boyutlarını ve eşleme modlarını yönetir

- Kaydırma çubuğu iletilerine yanıt olarak otomatik olarak kaydırır

"Sayfa" için ne kadar kaydırılacağını (Kullanıcı bir kaydırma çubuğu Shaft 'e tıkladığında) ve bir "satır" (Kullanıcı bir kaydırma okuna tıkladığı zaman) belirtebilirsiniz. Bu değerleri görünümlerinizin yapısına uyacak şekilde planlayın. Örneğin, bir grafik görünümü için 1 piksellik artışlarla, metin belgelerindeki çizgi yüksekliğine göre artışlarla kaydırmak isteyebilirsiniz.

## <a name="scaling-a-view"></a><a name="_core_scaling_a_view"></a> Görünümü ölçekleme

Görünümün otomatik olarak çerçeve penceresinin boyutuna sığması istediğinizde, `CScrollView` kaydırma yerine ölçekleme için kullanabilirsiniz. Mantıksal Görünüm, pencerenin istemci alanına tam olarak sığması için uzatılır veya küçültülebilir. Ölçeklenen bir görünüm, kaydırma çubuklarına sahip değildir.

## <a name="see-also"></a>Ayrıca bkz.

[Görünümleri kullanma](../mfc/using-views.md)
