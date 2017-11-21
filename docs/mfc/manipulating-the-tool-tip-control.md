---
title: "Araç ipucunu denetimini düzenleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CToolTipCtrl class [MFC], manipulating tool tip attributes
- tool tips [MFC], attributes
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c932d90cd2d896ebfe861ccd21d67b0071293c64
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="manipulating-the-tool-tip-control"></a>Araç İpucunu Denetimini Düzenleme
Sınıf `CToolTipCtrl` bir grup üyesi çeşitli özniteliklerini denetim işlevleri sağlayan `CToolTipCtrl` nesne ve araç ipucu penceresi.  
  
 Açılır pencere, başlangıç ve araç ipucu pencereleri ayarlayın ve çağrıları ile alınan süreleri reshow [GetDelayTime](../mfc/reference/ctooltipctrl-class.md#getdelaytime) ve [SetDelayTime](../mfc/reference/ctooltipctrl-class.md#setdelaytime).  
  
 Aşağıdaki işlevleri ile araç ipucu windows görünümünü değiştirin:  
  
-   [GetMargin](../mfc/reference/ctooltipctrl-class.md#getmargin) ve [SetMargin](../mfc/reference/ctooltipctrl-class.md#setmargin) alır ve ayarlar araç ipucu kenarlık ve aracı arasındaki genişliği İpucu metni.  
  
-   [GetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#getmaxtipwidth) ve [SetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#setmaxtipwidth) aracının en büyük genişliği alır ve ayarlar penceresi ipucu.  
  
-   [GetTipBkColor](../mfc/reference/ctooltipctrl-class.md#gettipbkcolor) ve [SetTipBkColor](../mfc/reference/ctooltipctrl-class.md#settipbkcolor) aracı arka plan rengini alır ve ayarlar penceresi ipucu.  
  
-   [GetTipTextColor](../mfc/reference/ctooltipctrl-class.md#gettiptextcolor) ve [SetTipTextColor](../mfc/reference/ctooltipctrl-class.md#settiptextcolor) aracının metin rengini alır ve ayarlar penceresi ipucu.  
  
 Önemli iletileri gibi bildirim almak araç ipucu denetimi için sırayla **WM_LBUTTONXXX** iletileri, araç ipucunu denetimini iletileri geçiş gerekir. Bu geçiş için en iyi yöntem çağırmaya olduğu [CToolTipCtrl::RelayEvent](../mfc/reference/ctooltipctrl-class.md#relayevent), `PreTranslateMessage` sahibi penceresinin işlevi. Aşağıdaki örnek, olası bir yöntemi gösterir (araç ipucunu denetimini varsayılarak çağrılır `m_ToolTip`):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#41](../mfc/codesnippet/cpp/manipulating-the-tool-tip-control_1.cpp)]  
  
 Hemen bir araç ipucu penceresi kaldırmak için arama [Pop](../mfc/reference/ctooltipctrl-class.md#pop) üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolTipCtrl kullanma](../mfc/using-ctooltipctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

