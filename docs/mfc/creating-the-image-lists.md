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
ms.openlocfilehash: 53cf33a551dc95e7ed282b599673f627ff8a7b21
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220943"
---
# <a name="creating-the-image-lists"></a>Görüntü Listelerini Oluşturma
Görüntü listelerini oluşturma olup aynı kullandığınız [CListView](../mfc/reference/clistview-class.md) veya [CListCtrl](../mfc/reference/clistctrl-class.md).  
  
> [!NOTE]
>  Liste denetiminiz varsa listeleri yalnızca görüntü `LVS_ICON` stili.  
  
 Bir sınıf kullanma `CImageList` (tam boyutlu simgeler, küçük simgeleri ve durumlarını için) bir veya daha fazla görüntü listeleri oluşturmak için. Bkz [Cımagelist](../mfc/reference/cimagelist-class.md)görüp [liste görünümü görüntü listeler](/windows/desktop/Controls/using-list-view-controls) Windows SDK.  
  
 Çağrı [CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) her görüntü listesi; bir işaretçi uygun geçirmek `CImageList` nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

