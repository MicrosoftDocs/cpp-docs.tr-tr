---
title: Bir araç çubuğu denetiminde resim listeleri kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76325d2b078f51860cad7fa3fab61ed7c518a41c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="using-image-lists-in-a-toolbar-control"></a>Bir Araç Çubuğu Denetiminde Görüntü Listeleri Kullanma
Varsayılan olarak, bir toolbar denetimine düğme tarafından kullanılan görüntüleri tek bir bit eşlem olarak depolanır. Ancak, bir resim listeleri kümesinde düğme resimlerini de depolayabilir. Araç çubuğu denetimi nesnesi için üç ayrı bir görüntü listeleri kullanabilirsiniz:  
  
-   Görüntü listesi içerir görüntüler şu an etkin araç çubuğu düğmeleri için etkin.  
  
-   Görüntü listesi içerir görüntüler şu anda devre dışı araç çubuğu düğmeleri için devre dışı.  
  
-   Görüntü listesi içerir görüntüler şu anda vurgulanmıştır araç çubuğu düğmeleri için vurgulanır. Bu görüntü listesi yalnızca araç kullandığında kullanılır **TBSTYLE_FLAT** stili.  
  
 Bunları ile ilişkilendirdiğinizde bu görüntü listeleri araç çubuğu denetimi tarafından kullanılan `CToolBarCtrl` nesnesi. Bu ilişkilendirme çağrı yaparak gerçekleştirilir [CToolBarCtrl::SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist), [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist), ve [SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist).  
  
 Varsayılan olarak, MFC kullanır `CToolBar` MFC Uygulama araç çubukları uygulanacak sınıf. Ancak, `GetToolBarCtrl` üye işlevi, katıştırılmış almak için kullanılabilir `CToolBarCtrl` nesnesi. Ardından çağrı yapmak `CToolBarCtrl` döndürülen nesne kullanarak üye işlevleri.  
  
 Aşağıdaki örnek, bir etkin atayarak bu tekniği gösterir (`m_ToolBarImages`) ve devre dışı bırakıldı (`m_ToolBarDisabledImages`) için resim listesi bir `CToolBarCtrl` nesne (`m_ToolBarCtrl`).  
  
 [!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]  
  
> [!NOTE]
>  Araç çubuğu nesnesi tarafından kullanılan resim listeleri kalıcı nesneler olması gerekir. Bu nedenle, bunlar genellikle bir MFC sınıfı veri üyesi olan; Bu örnekte, ana çerçeve pencere sınıfı.  
  
 Görüntü listeleri ilişkili sonra `CToolBarCtrl` nesne framework otomatik olarak uygun düğme resminin görüntüler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolBarCtrl kullanma](../mfc/using-ctoolbarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

