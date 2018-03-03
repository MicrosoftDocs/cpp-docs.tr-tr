---
title: "Liste öğeleri ve resim listeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 525d8353c308796d70f974fa56cde3aa76c12142
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="list-items-and-image-lists"></a>Liste Öğeleri ve Görüntü Listeleri
Liste denetiminde bir "öğesi" ([CListCtrl](../mfc/reference/clistctrl-class.md)) bir simge, bir etiket ve büyük olasılıkla diğer bilgileri ("alt öğeler") oluşur.  
  
 Liste denetim öğeleri simgelerini görüntü listelerinde yer alır. Bir resim listesi simge görünümünde kullanılan tam boyutlu simgeler içeriyor. İkinci, isteğe bağlı, görüntü listesi denetimi diğer görünümleri kullanmak için aynı simgeleri küçük sürümlerini içerir. Üçüncü bir isteğe bağlı listesi gibi belirli görünümlerde küçük simgeler önünde görüntülemek için onay kutularını "Durum" görüntüleri içerir. Liste denetimi bağımsız üstbilgi öğelerde görüntülenen görüntüleri dördüncü isteğe bağlı listesini içerir.  
  
> [!NOTE]
>  Liste Görünümü denetimi ile oluşturulursa `LVS_SHAREIMAGELISTS` stili, artık kullanımda olduğunda, görüntü listeleri yok etme için sorumlu. Birden çok liste görünümü denetimleri aynı görüntü atadığınızda, bu stili listeler belirtin; Aksi takdirde, birden fazla denetim aynı resim listesi yok etmek deneyebilirsiniz.  
  
 Liste öğeleri hakkında daha fazla bilgi için bkz: [liste görünümü görüntü listeleri](http://msdn.microsoft.com/library/windows/desktop/bb774736) ve [öğeleri ve alt öğeler](http://msdn.microsoft.com/library/windows/desktop/bb774736) Windows SDK'sındaki. Ayrıca bkz [Cımagelist](../mfc/reference/cimagelist-class.md) içinde *MFC başvurusu* ve [kullanarak Cımagelist](../mfc/using-cimagelist.md) makalelerin bu ailedeki.  
  
 Liste denetimi oluşturmak için listeye yeni öğeler eklemek için kullanılan görüntü listeleri sağlamanız gerekir. Bu yordam, aşağıdaki örnekte gösterilmiştir nerede `m_pImagelist` işaretçi türü `CImageList` ve `m_listctrl` olan bir `CListCtrl` veri üyesi.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/cpp/list-items-and-image-lists_1.cpp)]  
  
 Ancak, liste görünümü veya liste denetimi simgeleri göstermek planlamıyorsanız görüntü listeleri gerekmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

