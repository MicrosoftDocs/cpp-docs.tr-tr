---
title: Görüntü Listelerini Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: 52f375c98b5f73e0f5721c951c94e4b24f0bc224
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608686"
---
# <a name="creating-the-image-lists"></a>Görüntü Listelerini Oluşturma

Görüntü listelerini oluşturma olup aynı kullandığınız [CListView](../mfc/reference/clistview-class.md) veya [CListCtrl](../mfc/reference/clistctrl-class.md).

> [!NOTE]
>  Liste denetiminiz varsa listeleri yalnızca görüntü `LVS_ICON` stili.

Bir sınıf kullanma `CImageList` (tam boyutlu simgeler, küçük simgeleri ve durumlarını için) bir veya daha fazla görüntü listeleri oluşturmak için. Bkz [Cımagelist](../mfc/reference/cimagelist-class.md)görüp [liste görünümü görüntü listeler](/windows/desktop/Controls/using-list-view-controls) Windows SDK.

Çağrı [CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) her görüntü listesi; bir işaretçi uygun geçirmek `CImageList` nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

