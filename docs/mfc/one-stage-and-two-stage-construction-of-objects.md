---
title: Nesnelerin Tek Aşamalı ve İki Aşamalı Yapımı
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
ms.openlocfilehash: 8f221ac6b63a06c65f932a695dfbf7b93ae7ac96
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375977"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>Nesnelerin Tek Aşamalı ve İki Aşamalı Yapımı

Kalem ve fırçalar gibi grafik nesneleri oluşturmak için iki teknik arasında bir seçim vardır:

- *Tek aşamalı yapı*: Nesneyi bir aşamada, tüm oluşturucu ile inşa etmek ve baş harfe doğru leştirmek.

- *İki aşamalı yapı*: Nesneyi iki ayrı aşamada inşa eder ve başharfe ayırır. Oluşturucu nesneyi oluşturur ve bir başlatma işlevi nesneyi başharfe getirir.

İki aşamalı inşaat her zaman daha güvenlidir. Tek aşamalı yapıda, yanlış bağımsız değişkenler veya bellek ayırma başarısız olursa, oluşturucu bir özel durum atabilir. Bu sorun iki aşamalı inşaat tarafından önlenir, ancak başarısızlık için kontrol etmek zorunda. Her iki durumda da, nesneyi yok etmek aynı işlemdir.

> [!NOTE]
> Bu teknikler, yalnızca grafik nesneleri değil, herhangi bir nesne oluşturmak için geçerlidir.

## <a name="example-of-both-construction-techniques"></a>Her Iki Yapım Tekniği Örneği

Aşağıdaki kısa örnekte, kalem nesnesi oluşturma yöntemi her iki yöntemi de gösterilmektedir:

[!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Grafik nesneler](../mfc/graphic-objects.md)

- [Bir cihaz bağlamına grafik nesnesi seçme](../mfc/selecting-a-graphic-object-into-a-device-context.md)

- [Cihaz bağlamları](../mfc/device-contexts.md)

- [Görünümde Çizim](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>Ayrıca bkz.

[Grafik Nesneler](../mfc/graphic-objects.md)
