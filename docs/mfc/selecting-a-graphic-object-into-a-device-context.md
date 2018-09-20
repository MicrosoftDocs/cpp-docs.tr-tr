---
title: Bir cihaz bağlamına grafik nesnesi seçme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 406c4e7cd87b350f9317022dcf1821fa92ddf4af
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427673"
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

