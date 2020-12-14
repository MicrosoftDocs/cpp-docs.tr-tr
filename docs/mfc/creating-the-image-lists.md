---
description: 'Hakkında daha fazla bilgi edinin: görüntü listeleri oluşturma'
title: Görüntü Listelerini Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: f2776902e7be06161bdbcfad23bd21d9188467f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309673"
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
