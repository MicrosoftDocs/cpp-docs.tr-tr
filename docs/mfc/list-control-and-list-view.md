---
title: "Liste denetimi ve liste görünümü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CListView class [MFC], and CListCtrl
- views [MFC], list and list control
- CListCtrl class [MFC], and CListView
- list views [MFC]
- list controls [MFC], List view
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 46c9d559d642b6edf926b9feb49332ef7ec2924a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="list-control-and-list-view"></a>Liste Denetimi ve Liste Görünümü
Kolaylık olması için iki yolla liste denetimi MFC yalıtır. Liste denetimleri kullanabilirsiniz:  
  
-   Katıştırma tarafından doğrudan bir [CListCtrl](../mfc/reference/clistctrl-class.md) iletişim kutusu sınıfı nesne.  
  
-   Sınıf kullanarak dolaylı olarak [CListView](../mfc/reference/clistview-class.md).  
  
 `CListView`Liste denetimi denetimi Kapsüllenen MFC belge/görünüm mimarisi ile tümleştirmek kadar kolaylaştırır [CEditView](../mfc/reference/ceditview-class.md) düzenleme denetimi yalıtır: denetim MFC Görünümü tüm yüzey alanını doldurur. (Görünümü *olan* için cast denetim `CListView`.)  
  
 A `CListView` nesne devraldığı [CCtrlView](../mfc/reference/cctrlview-class.md) ve bunun temel sınıfları ve temel alınan liste denetimini almak için bir üye fonksiyonu ekler. Görünüm üyeleri görünüm olarak çalışmak için kullanır. Kullanım [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl) listesi denetimin üye işlevleri erişmek için üye işlevi. Bu üyeler için kullanın:  
  
-   Eklemek, silmek veya listesinde "öğeler" yönlendirebilir.  
  
-   Ayarlayın veya liste denetim öznitelikleri alın.  
  
 Bir başvuru almak için `CListCtrl` temel bir `CListView`, çağrı `GetListCtrl` , liste görünümü sınıfından:  
  
 [!code-cpp[NVC_MFCListView#4](../atl/reference/codesnippet/cpp/list-control-and-list-view_1.cpp)]  
  
 Bu konu, liste denetimi kullanmak için her iki yönde açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

