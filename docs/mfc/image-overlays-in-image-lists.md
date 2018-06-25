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
ms.openlocfilehash: 93d37b49a949ab29e0ae888d9c961da086ee4ca4
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928602"
---
# <a name="image-overlays-in-image-lists"></a>Görüntü Listelerindeki Görüntü Yer Paylaşımları
Her resim listesi ([Cımagelist](../mfc/reference/cimagelist-class.md)) katmana maskeleri olarak kullanılacak görüntüleri listesini içerir. Bir "katman" saydam başka bir görüntü çizilmiş bir görüntü maskesidir. Herhangi bir görüntü bir katmana maske olarak kullanılabilir. Resim listesi başına en fazla dört katmana maskeleri belirtebilirsiniz.  
  
 Kullanarak bir görüntünün dizinini katmana maskeleri listesine eklemek [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) üye işlevi, bir görüntünün dizinini ve bir katmana maskesi dizini. Katmana maskeleri dizinlerini tabanlı yerine sıfır tabanlı olduğunu unutmayın.  
  
 Tek bir çağrı kullanarak görüntü üzerinde bir katmana maskesi çizin `Draw`. Parametreleri çizin için görüntünün dizinini ve bir katmana maskesi dizini içerir. Kullanmalısınız [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) makrosu katmana maskesi dizinini belirtin. Bir katmana görüntü çağrılırken belirtebilirsiniz [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect) üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cımagelist kullanma](../mfc/using-cimagelist.md)   
 [Denetimler](../mfc/controls-mfc.md)

