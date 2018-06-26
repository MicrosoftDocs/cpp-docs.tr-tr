---
title: Yansımış iletileri işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b317f4c1b55e04f61aa0639bbd6953e5f36187a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931846"
---
# <a name="handling-reflected-messages"></a>Yansımış İletileri İşleme
Yansıma bir denetimin iletileri gibi işlemenize olanak tanır ileti **WM_CTLCOLOR**, **WM_COMMAND**, ve **wm_notıfy**, denetimin kendi içinde. Daha fazla kendine içinde ve taşınabilir denetimi yapar. Windows ortak denetimleri ile ve aynı zamanda (eski adıyla OLE denetimleri) ActiveX denetimleriyle mekanizması çalışır.  
  
 İleti yansıma yeniden kullanmanıza olanak tanır, `CWnd`-türetilmiş sınıfları daha kolay. İleti yansıma works aracılığıyla [CWnd::OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify), özel kullanarak **ON_XXX_REFLECT** iletisi eşleme girdilerini: Örneğin, **ON_CTLCOLOR_REFLECT** ve **ON_CONTROL_REFLECT**. [Teknik Not 62](../mfc/tn062-message-reflection-for-windows-controls.md) ileti yansıması daha ayrıntılı açıklanır.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz  
  
-   [İleti yansıması hakkında daha fazla bilgi edinin](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Bir ortak denetimi için ileti yansıması uygulama](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [ActiveX denetimi için ileti yansıması uygulama](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)
