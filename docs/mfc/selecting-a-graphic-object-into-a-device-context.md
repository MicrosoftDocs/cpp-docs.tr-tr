---
title: Bir Cihaz Bağlamına Grafik Nesnesi Seçme
ms.date: 11/04/2016
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
ms.openlocfilehash: c879369d445a9330139eff89be4ad8153252bfa1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438834"
---
# <a name="selecting-a-graphic-object-into-a-device-context"></a>Bir Cihaz Bağlamına Grafik Nesnesi Seçme

Bu konu, bir pencerenin cihaz bağlamında grafik nesneleri kullanarak geçerlidir. Çalıştırdıktan sonra [Titizlik oluşturma](../mfc/one-stage-and-two-stage-construction-of-objects.md), depolanan varsayılan nesne yerine cihaz bağlamına seçmelisiniz:

[!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/cpp/selecting-a-graphic-object-into-a-device-context_1.cpp)]

## <a name="lifetime-of-graphic-objects"></a>Grafik nesnelerin ömrü

Grafik nesne tarafından döndürülen [SelectObject](../mfc/reference/cdc-class.md#selectobject) "geçici." Diğer bir deyişle, tarafından silinecek [ONIDLE](../mfc/reference/cwinapp-class.md#onidle) sınıfının üye işlevinde `CWinApp` program alır boşta başlattığınızda zaman. Tarafından döndürülen nesne kullandığınız sürece `SelectObject` denetimi için ana ileti döngüsü döndürmeden olmadan tek işlevi içinde bir sorun olacaktır.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Grafik nesneler](../mfc/graphic-objects.md)

- [Grafik nesnelerin tek aşamalı ve iki aşamalı yapımı](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [Cihaz bağlamları](../mfc/device-contexts.md)

- [Bir Görünümde Çizim Yapma](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Grafik Nesneler](../mfc/graphic-objects.md)

