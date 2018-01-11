---
title: "Görüntü listelerini oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bfb42dc2c14b5092aeb667ea22008abe4d581a6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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

