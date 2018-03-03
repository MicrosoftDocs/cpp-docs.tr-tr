---
title: "Araç çubuğu denetimiyle çalışma | Microsoft Docs"
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
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 475b44b856c874064a4ccbdaf7b648342eb9c657
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="working-with-the-toolbar-control"></a>Araç Çubuğu Denetimiyle Çalışma
Bu makalede nasıl erişebileceğinizi açıklanmaktadır [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesnesinin altındaki bir [CToolBar](../mfc/reference/ctoolbar-class.md) çubuklarınızı üzerinde daha fazla denetim için. Bu gelişmiş bir konudur.  
  
## <a name="procedures"></a>Yordamlar  
  
#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>CToolBar nesnenizin temel araç yaygın bir denetim erişmek için  
  
1.  Çağrı [CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl).  
  
 `GetToolBarCtrl`bir başvuru döndürür bir [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesnesi. Araç çubuğu denetimi sınıfının üye işlevleri çağırmak için başvuru kullanabilirsiniz.  
  
> [!CAUTION]
>  Arama sırasında `CToolBarCtrl` **almak** işlevleri güvenli, çağırırsanız dikkatli **ayarlamak** işlevleri. Bu gelişmiş bir konudur. Normalde erişim temel araç çubuğu denetimi gerek yoktur.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Denetimleri (Windows ortak denetimleri)](../mfc/controls-mfc.md)  
  
-   [Araç çubuğu temelleri](../mfc/toolbar-fundamentals.md)  
  
-   [Yerleşen ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)  
  
-   [Araç çubuğu dinamik olarak yeniden boyutlandırma](../mfc/docking-and-floating-toolbars.md)  
  
-   [Araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md)  
  
-   [Flyby durum çubuğu güncelleştirmeleri](../mfc/toolbar-tool-tips.md)  
  
-   [Araç İpucu bildirimlerini işleme](../mfc/handling-tool-tip-notifications.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sınıfları  
  
-   [Özelleştirme bildirimlerini işleme](../mfc/handling-customization-notifications.md)  
  
-   [Birden çok araç çubukları](../mfc/toolbar-fundamentals.md)  
  
-   [Eski araç çubuklarınızı kullanma](../mfc/using-your-old-toolbars.md)  
  
-   [Denetim çubukları](../mfc/control-bars.md)  
  
 Windows ortak denetimleri kullanma hakkında genel bilgi için bkz: [ortak denetimleri](http://msdn.microsoft.com/library/windows/desktop/bb775493).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Araç Çubuğu Uygulaması](../mfc/mfc-toolbar-implementation.md)

