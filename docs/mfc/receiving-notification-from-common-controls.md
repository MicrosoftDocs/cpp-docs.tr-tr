---
title: Ortak denetimlerden bildirim alma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
dev_langs: C++
helpviewer_keywords:
- OnNotify method [MFC]
- common controls [MFC], notifications
- ON_NOTIFY macro [MFC]
- controls [MFC], notifications
- receiving notifications from common controls
- notifications [MFC], common controls
- Windows common controls [MFC], notifications
- WM_NOTIFY message
ms.assetid: 50194592-d60d-44d0-8ab3-338a2a2c63e7
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 19c75abb6c01f16433bb4f48a81b257e05dbf83e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="receiving-notification-from-common-controls"></a>Ortak Denetimlerden Bildirim Alma
Ortak Denetimler, denetimi, kullanıcı girişi gibi olaylar meydana geldiğinde, ana pencereyi bildirim iletilerini göndermek alt öğe pencerelerini ' dir.  
  
 Uygulamayı hangi eylemini kullanıcının gerçekleştirecek şekilde istediği belirlemek için bu bildirim iletilerini kullanır. En yaygın denetimleri olarak bildirim iletilerini göndermek **wm_notıfy** iletileri. Windows denetimleri olarak birçok bildirim iletilerini göndermek **WM_COMMAND** iletileri. [CWnd::OnNotify](../mfc/reference/cwnd-class.md#onnotify) için işleyicisidir **wm_notıfy** ileti. İle `CWnd::OnCommand`, uygulanması `OnNotify` bildirim iletisi gönderir `OnCmdMsg` ileti eşlemeleri işleme. Bildirimleri işleme için ileti eşleme girişi `ON_NOTIFY`. Daha fazla bilgi için bkz: [Teknik Not 61: on_notıfy ve wm_notıfy iletileri](../mfc/tn061-on-notify-and-wm-notify-messages.md).  
  
 Alternatif olarak, türetilmiş bir sınıf "ileti yansıması" kullanarak kendi bildirim iletilerini işleyebilir Daha fazla bilgi için bkz: [Teknik Not 62: Windows denetimleri için ileti yansıması](../mfc/tn062-message-reflection-for-windows-controls.md).  
  
## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>Bir bildirim iletisi imleç konumu alma  
 Bazen, belirli bildirim iletileri bir ortak denetimi tarafından alındığında imleci geçerli konumunu belirlemek kullanışlıdır. Örneğin, bir ortak denetimi aldığında, geçerli imleç konumu belirlemek yararlı olacaktır bir **nm_rclıck** bildirim iletisi.  
  
 Bunu çağırarak gerçekleştirmek için basit bir yolu yoktur `CWnd::GetCurrentMessage`. Ancak, bu yöntem yalnızca iletinin gönderildiği aynı anda imleç konumu alır. Çağırmanız gerekir ileti gönderildiğinde bu yana imleci taşınmış olabilir çünkü **CWnd::GetCursorPos** geçerli imleç konumu alınamıyor.  
  
> [!NOTE]
>  `CWnd::GetCurrentMessage`yalnızca içinde bir ileti işleyicisini çağrılmalıdır.  
  
 Bildirim ileti işleyicisi gövdesi için aşağıdaki kodu ekleyin (Bu örnekte, **nm_rclıck**):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]  
  
 Bu noktada, fare imleci konumu depolanan `cursorPos` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetimleri yapma ve kullanma](../mfc/making-and-using-controls.md)   
 [Denetimleri](../mfc/controls-mfc.md)

