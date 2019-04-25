---
title: Nesnelerin Tek Aşamalı ve İki Aşamalı Yapımı
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
ms.openlocfilehash: 871db7abd2682d557bf2e80e9cb97624f0dc53a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160165"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>Nesnelerin Tek Aşamalı ve İki Aşamalı Yapımı

Arasında kalemler ve fırçalar gibi grafik nesneleri oluşturmak için iki teknik vardır:

- *Tek aşamalı yapımı*: Oluşturun ve tüm oluşturucusuna sahip bir aşamada nesnesini başlatır.

- *İki aşamalı yapımı*: Oluşturun ve iki ayrı aşamada nesnesini başlatır. Oluşturucu nesnesi oluşturur ve bunu bir başlangıç işlevini başlatır.

İki aşamalı yapımı her zaman daha güvenlidir. Tek aşamalı oluşturma, oluşturucu bağlanamazsa özel durum yanlış bağımsız değişkenleri sağlayın veya bellek ayırma başarısız. Bu sorun, hata için denetlenecek sahip, ancak iki aşamalı yapımı tarafından önlenmiş olur. Her iki durumda da, nesneyi yok etmek aynı işlemdir.

> [!NOTE]
>  Bu teknikler, tüm nesneler, yalnızca grafik nesneleri oluşturmaya uygulayın.

## <a name="example-of-both-construction-techniques"></a>Her iki yapı teknikleri örneği

Bir pen nesnesi oluşturmak, her iki yöntem de aşağıdaki kısa örnek gösterilmektedir:

[!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Grafik nesneler](../mfc/graphic-objects.md)

- [Bir cihaz bağlamına grafik nesnesi seçme](../mfc/selecting-a-graphic-object-into-a-device-context.md)

- [Cihaz bağlamları](../mfc/device-contexts.md)

- [Bir Görünümde Çizim Yapma](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>Ayrıca bkz.

[Grafik Nesneler](../mfc/graphic-objects.md)
