---
title: Ortak denetimlerden bildirim alma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25979ec1157a4d2beedf96875e6c8c270b3aaaa9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442389"
---
# <a name="receiving-notification-from-common-controls"></a>Ortak Denetimlerden Bildirim Alma

Ortak Denetimler, denetimi, kullanıcı girişi gibi olaylar meydana geldiğinde bildirim iletilerini göndermek için ana pencerenin alt windows değil.

Uygulama, kullanıcının olması için hangi eylemin istediği belirlemek için bu bildirim iletilerini kullanır. En yaygın denetimler wm_notıfy iletileri bildirim iletilerini göndermek. Windows denetimleri WM_COMMAND iletileri olarak birçok bildirim iletilerini göndermek. [CWnd::OnNotify](../mfc/reference/cwnd-class.md#onnotify) wm_notıfy iletisi için bir işleyici. Olduğu gibi `CWnd::OnCommand`, uygulanması `OnNotify` bildirim iletisi gönderir `OnCmdMsg` ileti eşlemeleri işlemede için. Bildirimleri işleme için ileti eşlemesi on_notıfy girdidir. Daha fazla bilgi için [Teknik Not 61: on_notıfy ve wm_notıfy iletileri](../mfc/tn061-on-notify-and-wm-notify-messages.md).

Alternatif olarak, türetilmiş bir sınıf "ileti yansıması" kullanarak kendi bildirim iletileri işleyebilir Daha fazla bilgi için [Teknik Not 62: Windows denetimleri için ileti yansıması](../mfc/tn062-message-reflection-for-windows-controls.md).

## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>İmleç konumu bir bildirim iletisi alınıyor

Bazen, belirli uyarı iletilerini bir ortak denetimi tarafından alındığında, imleci geçerli konumunu belirlemek yararlıdır. Örneğin, bir ortak denetimi nm_rclıck bildirimi iletisi aldığında, geçerli imleç konumu belirlemek yararlı olacaktır.

Çağrı yaparak bunu sağlamak için basit bir yolu yoktur `CWnd::GetCurrentMessage`. Ancak, bu yöntem yalnızca iletinin gönderildiği zaman imleç konumu alır. İleti çağırmanız gönderildikten sonra imleç taşınmış olabilir çünkü `CWnd::GetCursorPos` geçerli imleç konumu alınamıyor.

> [!NOTE]
>  `CWnd::GetCurrentMessage` yalnızca bir ileti işleyicisi çağrılmalıdır.

(Bu örnekte, nm_rclıck) bildirim ileti işleyicisi gövdesine aşağıdaki kodu ekleyin:

[!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]

Bu noktada, fare imleci konumu depolanan `cursorPos` nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[Denetimleri Yapma ve Kullanma](../mfc/making-and-using-controls.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

