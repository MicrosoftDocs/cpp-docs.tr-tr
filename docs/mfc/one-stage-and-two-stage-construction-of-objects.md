---
title: Nesnelerin Tek Aşamalı ve İki Aşamalı Yapımı
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
ms.openlocfilehash: bdfb7879bc926435bdcd72d6776646c449ffef80
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623320"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>Nesnelerin Tek Aşamalı ve İki Aşamalı Yapımı

Arasında kalemler ve fırçalar gibi grafik nesneleri oluşturmak için iki teknik vardır:

- *Tek aşamalı yapımı*: yapısı ve tüm Oluşturucu ile tek bir aşamada nesne başlatılamadı.

- *İki aşamalı yapımı*: yapısı ve iki ayrı aşamadan içinde nesne başlatılamadı. Oluşturucu nesnesi oluşturur ve bunu bir başlangıç işlevini başlatır.

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

## <a name="see-also"></a>Ayrıca Bkz.

[Grafik Nesneler](../mfc/graphic-objects.md)

