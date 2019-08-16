---
title: Görüntü Listelerini Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: 6687b62b70103894d957a21019008e8781385feb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508789"
---
# <a name="creating-the-image-lists"></a>Görüntü Listelerini Oluşturma

Görüntü listelerinin oluşturulması, [Clienstview](../mfc/reference/clistview-class.md) veya [CListCtrl](../mfc/reference/clistctrl-class.md)tuşlarını kullanmanıza bakılmaksızın aynıdır.

> [!NOTE]
>  Yalnızca liste denetiminiz `LVS_ICON` stili içeriyorsa, görüntü listelerine ihtiyacınız vardır.

Bir veya `CImageList` daha fazla görüntü listesi oluşturmak için sınıfı kullanın (tam boyutlu simgeler, küçük simgeler ve durumlar için). Bkz. [CImageList](../mfc/reference/cimagelist-class.md)ve Windows SDK [liste görünümü görüntü listeleri](/windows/win32/Controls/using-list-view-controls) .

Her görüntü listesi için [Clienstctrl:: SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) ' i çağırın; uygun `CImageList` nesneye bir işaretçi geçirin.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
