---
title: Görüntü listelerini oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e5f5ac8396c32e56e4c0f2f951f45bb33714822
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341531"
---
# <a name="creating-the-image-lists"></a>Görüntü Listelerini Oluşturma
Görüntü listelerini oluşturma olup aynı kullandığınız [CListView](../mfc/reference/clistview-class.md) veya [CListCtrl](../mfc/reference/clistctrl-class.md).  
  
> [!NOTE]
>  Liste denetimi içeriyorsa listeler yalnızca görüntü `LVS_ICON` stili.  
  
 Bir sınıf kullanma `CImageList` bir veya daha fazla görüntü listeleri (için tam boyutlu simgeler, küçük simgeler ve durumlarını) oluşturmak için. Bkz: [Cımagelist](../mfc/reference/cimagelist-class.md)ve [liste görünümü görüntü listeleri](http://msdn.microsoft.com/library/windows/desktop/bb774736) Windows SDK'sındaki.  
  
 Çağrı [CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) her görüntü listesi; bir işaretçi uygun geçirmek `CImageList` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

