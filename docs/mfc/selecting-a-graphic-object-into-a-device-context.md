---
description: 'Hakkında daha fazla bilgi edinin: bir cihaz bağlamına grafik nesnesi seçme'
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
ms.openlocfilehash: cc2aabbcb1614fc77e5eadf9e6fba13ba377a4c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217685"
---
# <a name="selecting-a-graphic-object-into-a-device-context"></a>Bir Cihaz Bağlamına Grafik Nesnesi Seçme

Bu konu, bir pencerenin cihaz bağlamındaki grafik nesnelerini kullanmak için geçerlidir. [Bir çizim nesnesi](../mfc/one-stage-and-two-stage-construction-of-objects.md)oluşturduktan sonra, burada depolanan varsayılan nesne yerine cihaz bağlamına seçmeniz gerekir:

[!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/cpp/selecting-a-graphic-object-into-a-device-context_1.cpp)]

## <a name="lifetime-of-graphic-objects"></a>Grafik nesnelerinin ömrü

[NesneSeç](../mfc/reference/cdc-class.md#selectobject) tarafından döndürülen grafik nesnesi "geçici" tir. Diğer bir deyişle, program, bir sonraki boşta kalma süresi dolduğunda sınıfının [OnIdle](../mfc/reference/cwinapp-class.md#onidle) üye işlevi tarafından silinir `CWinApp` . `SelectObject`Ana ileti döngüsüne denetim döndürmeden tek bir işlevde tarafından döndürülen nesneyi kullandığınız sürece, sorun olmayacaktır.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Grafik nesneler](../mfc/graphic-objects.md)

- [Grafik nesnelerinin tek aşamalı ve iki aşamalı yapımı](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [Cihaz bağlamları](../mfc/device-contexts.md)

- [Bir görünümde çizim yapma](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>Ayrıca bkz.

[Grafik nesneleri](../mfc/graphic-objects.md)
