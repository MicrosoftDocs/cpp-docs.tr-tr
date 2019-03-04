---
title: Görüntü Listelerini Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: 844bfe71f7b03f299f57b0fd4558b7e9eacf67c2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265788"
---
# <a name="creating-the-image-lists"></a>Görüntü Listelerini Oluşturma

Görüntü listelerini oluşturma olup aynı kullandığınız [CListView](../mfc/reference/clistview-class.md) veya [CListCtrl](../mfc/reference/clistctrl-class.md).

> [!NOTE]
>  Liste denetiminiz varsa listeleri yalnızca görüntü `LVS_ICON` stili.

Bir sınıf kullanma `CImageList` (tam boyutlu simgeler, küçük simgeleri ve durumlarını için) bir veya daha fazla görüntü listeleri oluşturmak için. Bkz [Cımagelist](../mfc/reference/cimagelist-class.md)görüp [liste görünümü görüntü listeler](/windows/desktop/Controls/using-list-view-controls) Windows SDK.

Çağrı [CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) her görüntü listesi; bir işaretçi uygun geçirmek `CImageList` nesne.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
