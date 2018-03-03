---
title: "CToolBarCtrl nesnesi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CToolBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e86fad8191c4dea2eed3ae34ec96ed853ac1deae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-ctoolbarctrl-object"></a>CToolBarCtrl Nesnesi Oluşturma
[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesneleri içeren birkaç iç veri yapılarını — düğmesi görüntü bit eşlemler listesini, düğmesi etiketi dizelerinin listesini ve listesini `TBBUTTON` yapıları —, görüntüyü ilişkilendirmek ve/veya konumu, stil, durum, dize ve düğmenin komut kimliği. Bu veri yapıları öğelerin her biri sıfır tabanlı dizini adlandırılır. Kullanabilmeniz için önce bir `CToolBarCtrl` nesnesi, bu veri yapıları ayarlamanız gerekir. Veri yapıları listesi için bkz: [araç çubuğu denetimleri](controls-mfc.md) Windows SDK. Dize listesi yalnızca düğme etiketleri için kullanılabilir; araç çubuğundan dizeleri alınamıyor.  
  
 Kullanılacak bir `CToolBarCtrl` nesnesi, genellikle şu adımları izleyin:  
  
### <a name="to-use-a-ctoolbarctrl-object"></a>CToolBarCtrl nesnesi kullanmak için  
  
1.  Oluşturmak [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesnesi.  
  
2.  Çağrı [oluşturma](../mfc/reference/ctoolbarctrl-class.md#create) Windows araç yaygın bir denetim oluşturmak ve ona eklemek için `CToolBarCtrl` nesnesi. Bit eşlem görüntüleri için düğmeler istiyorsanız, düğme bit eşlemler araç çubuğuna çağırarak eklemek [AddBitmap](../mfc/reference/ctoolbarctrl-class.md#addbitmap). Dize etiketleri için düğmeler istiyorsanız dizeleri araç çubuğuna çağırarak eklemek [AddString](../mfc/reference/ctoolbarctrl-class.md#addstring) ve/veya [AddStrings](../mfc/reference/ctoolbarctrl-class.md#addstrings). Çağırdıktan sonra `AddString` ve/veya `AddStrings`, çağırmalısınız [AutoSize](../mfc/reference/ctoolbarctrl-class.md#autosize) dize veya dizelerin görünmesine alabilmek için.  
  
3.  Düğme yapıları çağırarak araç çubuğuna ekleme [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons).  
  
4.  Araç ipuçları istiyorsanız, işleme **TTN_NEEDTEXT** açıklandığı gibi araç çubuğunun sahibi penceresinde iletileri [araç ipucu bildirimlerini işleme](../mfc/handling-tool-tip-notifications.md).  
  
5.  Araç çubuğunu özelleştirme yapabilmek için kullanıcının istiyorsanız, açıklandığı gibi sahip penceresinde özelleştirme bildirim iletilerini işleme [özelleştirme bildirimlerini işleme](../mfc/handling-customization-notifications.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolBarCtrl kullanma](../mfc/using-ctoolbarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

