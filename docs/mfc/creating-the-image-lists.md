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
ms.openlocfilehash: 4878caa735562a76bc4afe64b7d5bb1ecb22e069
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-the-image-lists"></a>Görüntü Listelerini Oluşturma
Görüntü listelerini oluşturma olup aynı kullandığınız [CListView](../mfc/reference/clistview-class.md) veya [CListCtrl](../mfc/reference/clistctrl-class.md).  
  
> [!NOTE]
>  Liste denetimi içeriyorsa listeler yalnızca görüntü `LVS_ICON` stili.  
  
 Bir sınıf kullanma `CImageList` bir veya daha fazla görüntü listeleri (için tam boyutlu simgeler, küçük simgeler ve durumlarını) oluşturmak için. Bkz: [Cımagelist](../mfc/reference/cimagelist-class.md)ve [liste görünümü görüntü listeleri](http://msdn.microsoft.com/library/windows/desktop/bb774736) Windows SDK'sındaki.  
  
 Çağrı [CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) her görüntü listesi; bir işaretçi uygun geçirmek `CImageList` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

