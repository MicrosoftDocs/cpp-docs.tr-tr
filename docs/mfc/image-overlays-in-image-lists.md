---
description: 'Daha fazla bilgi edinin: resim listelerinde görüntü Yerpaylaşımları'
title: Görüntü Listelerindeki Görüntü Yer Paylaşımları
ms.date: 11/04/2016
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
ms.openlocfilehash: dd65a27c9ef66311311195c1493e91be8c66d100
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290121"
---
# <a name="image-overlays-in-image-lists"></a>Görüntü Listelerindeki Görüntü Yer Paylaşımları

Her görüntü listesi ([CImageList](reference/cimagelist-class.md)), kaplama maskeleri olarak kullanılacak görüntülerin bir listesini içerir. "Yer paylaşımı maskesi", başka bir görüntünün üzerinde saydam olarak çizilen bir görüntüdür. Herhangi bir görüntü, bir kaplama maskesi olarak kullanılabilir. Her görüntü listesi için en fazla dört kaplama maskesi belirtebilirsiniz.

Bir görüntünün dizinini, [SetOverlayImage](reference/cimagelist-class.md#setoverlayimage) üye işlevini, bir görüntünün dizinini ve bir kaplama maskesinin dizinini kullanarak, kaplama maskeleri listesine eklersiniz. Yer paylaşımı maskeleri için dizin, sıfır tabanlı yerine tek tabanlı olduğunu unutmayın.

Tek bir çağrısı kullanarak bir görüntü üzerinde bir kaplama maskesi çizersiniz `Draw` . Parametreler, çizilecek görüntünün dizinini ve bir kaplama maskesinin dizinini içerir. Yer paylaşımı maskesinin dizinini belirtmek için [INDEXTOOVERLAYMASK](/windows/win32/api/commctrl/nf-commctrl-indextooverlaymask) makrosunu kullanmanız gerekir. Ayrıca, [DrawIndirect](reference/cimagelist-class.md#drawindirect) üye işlevini çağırırken bir kaplama görüntüsü de belirtebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CImageList Kullanma](using-cimagelist.md)<br/>
[Denetimler](controls-mfc.md)
