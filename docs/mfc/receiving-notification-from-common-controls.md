---
description: 'Hakkında daha fazla bilgi edinin: ortak denetimlerden bildirim alma'
title: Ortak Denetimlerden Bildirim Alma
ms.date: 11/04/2016
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
ms.openlocfilehash: a135dbc71447d31156ee4cfb223db410aad5218e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248560"
---
# <a name="receiving-notification-from-common-controls"></a>Ortak Denetimlerden Bildirim Alma

Ortak denetimler, Kullanıcı girişi gibi olaylar denetimde oluştuğunda ana pencereye bildirim iletileri gönderen alt Windows ' lardır.

Uygulama, kullanıcının yapması istediği eylemi belirlemek için bu bildirim iletilerini kullanır. Çoğu ortak denetim bildirim iletilerini WM_NOTIFY iletileri olarak gönderir. Windows denetimleri, çoğu bildirim iletisini WM_COMMAND ileti olarak gönderir. [CWnd:: OnNotify](../mfc/reference/cwnd-class.md#onnotify) , WM_NOTIFY ileti için işleyicidir. İle olduğu gibi `CWnd::OnCommand` , ' nin uygulanması `OnNotify` bildirim iletisini `OnCmdMsg` ileti eşlemelerinde işlemeye yönelik olarak gönderir. Bildirimleri işlemeye yönelik ileti eşleme girişi ON_NOTIFY. Daha fazla bilgi için bkz. [Teknik Note 61: ON_NOTIFY ve WM_NOTIFY iletileri](../mfc/tn061-on-notify-and-wm-notify-messages.md).

Alternatif olarak, türetilmiş bir sınıf "ileti yansıtma" kullanarak kendi bildirim iletilerini işleyebilir. Daha fazla bilgi için bkz. [Teknik not62: Windows denetimleri Için Ileti yansıması](../mfc/tn062-message-reflection-for-windows-controls.md).

## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>Bir bildirim Iletisinde Imleç konumunu alma

Bazen, belirli bildirim iletileri ortak bir denetim tarafından alındığında imlecin geçerli konumunu belirlenmesi yararlı olur. Örneğin, ortak bir denetim NM_RCLICK bildirim iletisi aldığında geçerli imleç konumunun belirlenmesi yararlı olacaktır.

Bunu çağırarak gerçekleştirmenin basit bir yolu vardır `CWnd::GetCurrentMessage` . Ancak, bu yöntem yalnızca iletinin gönderildiği sırada imleç konumunu alır. Çünkü ileti gönderildikten sonra imleç taşınmış olabileceğinden, `CWnd::GetCursorPos` geçerli imleç konumunu almak için çağrısı yapmanız gerekir.

> [!NOTE]
> `CWnd::GetCurrentMessage` yalnızca bir ileti işleyicisi içinde çağrılmalıdır.

Bildirim iletisi işleyicisinin gövdesine aşağıdaki kodu ekleyin (Bu örnekte, NM_RCLICK):

[!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]

Bu noktada, fare imleç konumu `cursorPos` nesnesinde depolanır.

## <a name="see-also"></a>Ayrıca bkz.

[Denetimleri yapma ve kullanma](../mfc/making-and-using-controls.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
