---
title: Görüntü Listelerini Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: bbba01a6a8e08ea53e164656733aa06e03dd87a7
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625946"
---
# <a name="creating-the-image-lists"></a>Görüntü Listelerini Oluşturma

Görüntü listelerinin oluşturulması, [Clienstview](reference/clistview-class.md) veya [CListCtrl](reference/clistctrl-class.md)tuşlarını kullanmanıza bakılmaksızın aynıdır.

> [!NOTE]
> Yalnızca liste denetiminiz stili içeriyorsa, görüntü listelerine ihtiyacınız vardır `LVS_ICON` .

`CImageList`Bir veya daha fazla görüntü listesi oluşturmak için sınıfı kullanın (tam boyutlu simgeler, küçük simgeler ve durumlar için). Bkz. [CImageList](reference/cimagelist-class.md)ve Windows SDK [liste görünümü görüntü listeleri](/windows/win32/Controls/using-list-view-controls) .

Her görüntü listesi için [Clienstctrl:: SetImageList](reference/clistctrl-class.md#setimagelist) ' i çağırın; uygun nesneye bir işaretçi geçirin `CImageList` .

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](using-clistctrl.md)<br/>
[Denetimler](controls-mfc.md)
