---
title: "Araç ipuçları oluşturma yöntemleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CToolTipCtrl class [MFC], creating tool tips
- tool tips [MFC], tool tip controls
- tool tips [MFC], creating
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: aed7972e361ceb4da3db2bf68020e49b78a752e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="methods-of-creating-tool-tips"></a>Araç İpuçları Oluşturma Yöntemleri
MFC sağlar oluşturmak ve Aracı'nı yönetmek için üç sınıfları ipucu denetimi: [CWnd](../mfc/reference/cwnd-class.md), [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md), [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) ve [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md). Araç İpucu üye işlevleri bu sınıfların Windows ortak denetim API'si sarılır. Sınıf `CToolBarCtrl` ve sınıf `CToolTipCtrl` sınıfından türetilen `CWnd`.  
  
 `CWnd`oluşturmak ve araç ipuçları yönetmek için dört üye işlevleri sağlar: [EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips), [CancelToolTips](../mfc/reference/cwnd-class.md#canceltooltips), [FilterToolTipMessage](../mfc/reference/cwnd-class.md#filtertooltipmessage), ve [ OnToolHitTest](../mfc/reference/cwnd-class.md#ontoolhittest). Bu tek tek üye işlevleri araç ipuçları nasıl uyguladıkları hakkında daha fazla bilgi için bkz.  
  
 Bir araç kullanarak oluşturursanız `CToolBarCtrl`, aşağıdaki üye işlevleri kullanarak doğrudan bu araç için araç ipuçları uygulayabilirsiniz: [GetToolTips](../mfc/reference/ctoolbarctrl-class.md#gettooltips) ve [SetToolTips](../mfc/reference/ctoolbarctrl-class.md#settooltips). Bu tek tek üye işlevleri bakın ve [araç ipucu bildirimlerini işleme](../mfc/handling-tool-tip-notifications.md) araç ipuçları nasıl uyguladıkları hakkında daha fazla bilgi.  
  
 `CToolTipCtrl` Sınıfı Windows ortak araç ipucunu denetimini işlevselliğini sağlar. Bir tek araç ipucunu denetimini birden fazla aracı için bilgi sağlayabilir. Alt pencere veya denetim ya da bir uygulama tanımlı dikdörtgen pencerenin istemci alanda gibi bir ya da penceresi aracıdır. [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md) sınıfı türer `CToolTipCtrl` ve ek görsel stilleri ve işlevsellik sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolTipCtrl kullanma](../mfc/using-ctooltipctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

