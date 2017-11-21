---
title: "Yansımış iletileri işleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 442e9f3ee7af696a175a57d482b2d276f10eb0b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="handling-reflected-messages"></a>Yansımış İletileri İşleme
Yansıma bir denetimin iletileri gibi işlemenize olanak tanır ileti `WM_CTLCOLOR`, **WM_COMMAND**, ve **wm_notıfy**, denetimin kendi içinde. Daha fazla kendine içinde ve taşınabilir denetimi yapar. Windows ortak denetimleri ile ve aynı zamanda (eski adıyla OLE denetimleri) ActiveX denetimleriyle mekanizması çalışır.  
  
 İleti yansıma yeniden kullanmanıza olanak tanır, `CWnd`-türetilmiş sınıfları daha kolay. İleti yansıma works aracılığıyla [CWnd::OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify), özel kullanarak **ON_XXX_REFLECT** iletisi eşleme girdilerini: Örneğin, **ON_CTLCOLOR_REFLECT** ve **ON_CONTROL_REFLECT**. [Teknik Not 62](../mfc/tn062-message-reflection-for-windows-controls.md) ileti yansıması daha ayrıntılı açıklanır.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz  
  
-   [İleti yansıması hakkında daha fazla bilgi edinin](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Bir ortak denetimi için ileti yansıması uygulama](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [ActiveX denetimi için ileti yansıması uygulama](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İleti işleyici işlevlerini bildirme](../mfc/declaring-message-handler-functions.md)
