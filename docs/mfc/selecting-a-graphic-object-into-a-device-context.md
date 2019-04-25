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
ms.openlocfilehash: 7fb1507c1200da4cdf44627557ff6993e927d51e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308540"
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

## <a name="see-also"></a>Ayrıca bkz.

[Grafik Nesneler](../mfc/graphic-objects.md)
