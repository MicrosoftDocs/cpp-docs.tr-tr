---
title: Rebar denetimiyle birlikte bir resim listesi kullanma | Microsoft Docs
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
- image lists [MFC], rebar controls
- rebar controls [MFC], image lists
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: acb4ed52982f7ab23dac044eeacf315f45aa1232
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-image-list-with-a-rebar-control"></a>Rebar Denetimiyle Birlikte Bir Görüntü Listesi Kullanma
Her rebar bant, bunun yanı sıra, ilişkili resim listesi görüntüden içerebilir. Aşağıdaki yordam bir rebar bant görüntüyü görüntülemek için gerekli adımları ayrıntılarını verir.  
  
### <a name="to-display-images-in-a-rebar-band"></a>Bir rebar bant görüntüleri göstermek için  
  
1.  Çağrı yaparak rebar denetimi nesnesine bir resim listesi ekleme [SetImageList](../mfc/reference/crebarctrl-class.md#setimagelist), varolan bir görüntü listesi bir işaretçi geçirme.  
  
2.  Değiştirme **REBARBANDINFO** yapısı görüntünün bir rebar bant atamak için:  
  
    -   Ayarlama **fMask** üyesine **RBBIM_IMAGE**, gerektiği gibi ek bayrakları dahil edilecek bit düzeyinde OR işleci kullanarak.  
  
    -   Ayarlama `iImage` görüntünün görüntü listesi dizini üyesine görüntülenecek.  
  
3.  Boyut, metin ve gerekli bilgilerin Kapsanan alt pencere tanıtıcısı gibi kalan tüm veri üyeleri başlatır.  
  
4.  (Resimli) yeni bant çağrısıyla Ekle [CReBarCtrl::InsertBand](../mfc/reference/crebarctrl-class.md#insertband), geçen **REBARBANDINFO** yapısı.  
  
 Aşağıdaki örnekte, iki görüntü varolan bir görüntü listesi nesnesiyle rebar denetimi nesneye iliştirilmiş olduğu varsayılır (`m_wndReBar`). Yeni bir rebar bant (tarafından tanımlanan `rbi`), ilk resmi içeren, çağrısıyla eklenen `InsertBand`:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/cpp/using-an-image-list-with-a-rebar-control_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CReBarCtrl kullanma](../mfc/using-crebarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

