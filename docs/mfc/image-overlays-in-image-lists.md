---
title: Görüntü listelerindeki görüntü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c4052e06fe8aae1d149c3c09e88715d8270b361
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426568"
---
# <a name="image-overlays-in-image-lists"></a>Görüntü Listelerindeki Görüntü Yer Paylaşımları

Her bir görüntü listesi ([Cımagelist](../mfc/reference/cimagelist-class.md)) katman maskeleri olarak kullanılacak görüntülerin bir listesini içerir. Bir "katman maskesi" şeffaf bir şekilde başka bir görüntünün üzerine çizilmiş bir görüntüsüdür. Herhangi bir görüntü, bir katman maskesi kullanılabilir. Görüntü listesi başına en fazla dört katman maskeleri belirtebilirsiniz.

Katman maskeleri listesine de bir görüntünün dizinini kullanarak eklemek [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) üye işlevi, bir görüntünün dizinini ve katman maskesi dizini. Katman maskeleri için dizin tabanlı yerine sıfır tabanlı olduğunu unutmayın.

Bir katman maskesi üzerinden tek bir çağrı kullanarak görüntü çizme `Draw`. Parametreleri çizmek için görüntünün dizinini ve katman maskesi dizinini içerir. Kullanmalısınız [INDEXTOOVERLAYMASK](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask) makrosuna katman maskesi dizinini belirtin. Bir katmana görüntü çağırırken belirtebilirsiniz [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect) üye işlevi.

## <a name="see-also"></a>Ayrıca Bkz.

[CImageList Kullanma](../mfc/using-cimagelist.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

