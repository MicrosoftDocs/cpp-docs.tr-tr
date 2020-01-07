---
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
ms.openlocfilehash: 73315d4a1107204bc6adc885729fdeeaeb7f98d0
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298980"
---
# <a name="receiving-notification-from-common-controls"></a>Ortak Denetimlerden Bildirim Alma

Ortak denetimler, Kullanıcı girişi gibi olaylar denetimde oluştuğunda ana pencereye bildirim iletileri gönderen alt Windows ' lardır.

Uygulama, kullanıcının yapması istediği eylemi belirlemek için bu bildirim iletilerini kullanır. Çoğu ortak denetim bildirim iletilerini WM_NOTIFY iletileri olarak gönderir. Windows denetimleri, çoğu bildirim iletisini WM_COMMAND ileti olarak gönderir. [CWnd:: OnNotify](../mfc/reference/cwnd-class.md#onnotify) , WM_NOTIFY ileti için işleyicidir. `CWnd::OnCommand`olduğu gibi, `OnNotify` uygulanması bildirim iletisini ileti eşlemlerinde işleme için `OnCmdMsg` gönderir. Bildirimleri işlemeye yönelik ileti eşleme girişi ON_NOTIFY. Daha fazla bilgi için bkz. [Teknik Note 61: ON_NOTIFY ve WM_NOTIFY iletileri](../mfc/tn061-on-notify-and-wm-notify-messages.md).

Alternatif olarak, türetilmiş bir sınıf "ileti yansıtma" kullanarak kendi bildirim iletilerini işleyebilir. Daha fazla bilgi için bkz. [Teknik not62: Windows denetimleri Için Ileti yansıması](../mfc/tn062-message-reflection-for-windows-controls.md).

## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>Bir bildirim Iletisinde Imleç konumunu alma

Bazen, belirli bildirim iletileri ortak bir denetim tarafından alındığında imlecin geçerli konumunu belirlenmesi yararlı olur. Örneğin, ortak bir denetim NM_RCLICK bildirim iletisi aldığında geçerli imleç konumunun belirlenmesi yararlı olacaktır.

`CWnd::GetCurrentMessage`çağırarak bunu gerçekleştirmenin basit bir yolu vardır. Ancak, bu yöntem yalnızca iletinin gönderildiği sırada imleç konumunu alır. İleti gönderildikten sonra imleç taşınmış olabileceğinden, geçerli imleç konumunu almak için `CWnd::GetCursorPos` çağırmanız gerekir.

> [!NOTE]
>  `CWnd::GetCurrentMessage` yalnızca bir ileti işleyicisi içinde çağrılmalıdır.

Bildirim iletisi işleyicisinin gövdesine aşağıdaki kodu ekleyin (Bu örnekte, NM_RCLICK):

[!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]

Bu noktada, fare imleç konumu `cursorPos` nesnesinde depolanır.

## <a name="see-also"></a>Ayrıca bkz.

[Denetimleri Yapma ve Kullanma](../mfc/making-and-using-controls.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
