---
title: Görüntü Listelerindeki Görüntü Yer Paylaşımları
ms.date: 11/04/2016
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
ms.openlocfilehash: ec795193a28a68d8aee61e9932481a89c4b3e8e0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508380"
---
# <a name="image-overlays-in-image-lists"></a>Görüntü Listelerindeki Görüntü Yer Paylaşımları

Her görüntü listesi ([CImageList](../mfc/reference/cimagelist-class.md)), kaplama maskeleri olarak kullanılacak görüntülerin bir listesini içerir. "Yer paylaşımı maskesi", başka bir görüntünün üzerinde saydam olarak çizilen bir görüntüdür. Herhangi bir görüntü, bir kaplama maskesi olarak kullanılabilir. Her görüntü listesi için en fazla dört kaplama maskesi belirtebilirsiniz.

Bir görüntünün dizinini, [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) üye işlevini, bir görüntünün dizinini ve bir kaplama maskesinin dizinini kullanarak, kaplama maskeleri listesine eklersiniz. Yer paylaşımı maskeleri için dizin, sıfır tabanlı yerine tek tabanlı olduğunu unutmayın.

Tek bir çağrısı `Draw`kullanarak bir görüntü üzerinde bir kaplama maskesi çizersiniz. Parametreler, çizilecek görüntünün dizinini ve bir kaplama maskesinin dizinini içerir. Yer paylaşımı maskesinin dizinini belirtmek için [INDEXTOOVERLAYMASK](/windows/win32/api/commctrl/nf-commctrl-indextooverlaymask) makrosunu kullanmanız gerekir. Ayrıca, [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect) üye işlevini çağırırken bir kaplama görüntüsü de belirtebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CImageList Kullanma](../mfc/using-cimagelist.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
