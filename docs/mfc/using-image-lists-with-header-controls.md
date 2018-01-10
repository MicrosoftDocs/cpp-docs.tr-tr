---
title: "Görüntü listeleri kullanma üstbilgi denetimleriyle birlikte | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- header controls [MFC], image lists
- CHeaderCtrl class [MFC], image lists
- image lists [MFC], header controls
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a7a51aadc10a7722875597813e24ceb5960ab459
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-image-lists-with-header-controls"></a>Üstbilgi Denetimleriyle Birlikte Görüntü Listeleri Kullanma
Üstbilgi öğeleri bir görüntüyü üstbilgi öğesi içinde seçeneğine sahipsiniz. Bir ilişkili görüntü listesinde depolanan bu görüntüsü 16 x 16 piksel ve liste görünümü denetimi içinde kullanılan simge görüntüleri aynı özelliklere sahip. Bu davranış başarıyla uygulamak için ilk oluşturun ve resim listesi başlatma listesi üstbilgi denetimiyle ilişkilendirmek ve görüntünün görüntüler üstbilgi öğesi özniteliklerini değiştirme gerekir.  
  
 Aşağıdaki yordam bir üstbilgi denetimi için bir işaretçi kullanarak ayrıntılarını gösterir (`m_pHdrCtrl`) ve bir işaretçi bir resim listesi için (`m_pHdrImages`).  
  
### <a name="to-display-an-image-in-a-header-item"></a>Bir üstbilgi öğesi bir resmi görüntülemek için  
  
1.  Yeni bir görüntü listesi oluşturun (veya varolan bir görüntü listesi nesnesini kullanın) kullanarak [Cımagelist](../mfc/reference/cimagelist-class.md) sonuç işaretçi depolama Oluşturucusu.  
  
2.  Çağırarak yeni görüntü listesi nesnesi başlatılmaya [CImageList::Create](../mfc/reference/cimagelist-class.md#create). Aşağıdaki kod, bu çağrının bir örnektir.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]  
  
3.  Her üstbilgi öğesi için görüntüleri ekleyin. Aşağıdaki kod iki önceden tanımlanmış görüntüler ekler.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]  
  
4.  Üstbilgi denetimi çağrısıyla resim listesi ilişkilendirmek [CHeaderCtrl::SetImageList](../mfc/reference/cheaderctrl-class.md#setimagelist).  
  
5.  İlişkili resim listesinden resim görüntülemek için üstbilgi öğesi değiştirin. Aşağıdaki örnek, gelen ilk görüntünün atar `m_phdrImages`, ilk üstbilgi öğesi için `m_pHdrCtrl`.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]  
  
 Kullanılan parametre değerleri hakkında ayrıntılı bilgi için ilgili başvurun [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md).  
  
> [!NOTE]
>  Birden çok denetim aynı görüntü listesi kullanma olması mümkündür. Örneğin, standart liste görünümü denetimi olabilir hem küçük simge görünümünü liste görünümü denetimi ve liste görünümü denetimi, üstbilgi öğeleri tarafından kullanılan bir görüntü listesi (16 x 16 piksel görüntüleri için).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)

