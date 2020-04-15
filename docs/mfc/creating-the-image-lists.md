---
title: Görüntü Listelerini Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: 440ab6fdfe7663557f6c6a6607e617c793d26674
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371582"
---
# <a name="creating-the-image-lists"></a>Görüntü Listelerini Oluşturma

[CListView](../mfc/reference/clistview-class.md) veya [CListCtrl'i](../mfc/reference/clistctrl-class.md)kullanıp kullanmadığınız da resim listeleri oluşturmakla aynıdır.

> [!NOTE]
> Yalnızca liste denetiminiz stili içeriyorsa resim listelerine `LVS_ICON` ihtiyacınız vardır.

Bir `CImageList` veya daha fazla resim listesi oluşturmak için sınıfı kullanın (tam boyutlu simgeler, küçük simgeler ve durumlar için). [CImageList'e](../mfc/reference/cimagelist-class.md)bakın ve Windows SDK'daki [Liste Görünümü Resim Listeleri'ne](/windows/win32/Controls/using-list-view-controls) bakın.

[CListCtrl'i arayın::Her](../mfc/reference/clistctrl-class.md#setimagelist) resim listesi için SetImageList; uygun `CImageList` nesneye bir işaretçi geçirin.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
