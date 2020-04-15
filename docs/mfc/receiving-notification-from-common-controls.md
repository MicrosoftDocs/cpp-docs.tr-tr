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
ms.openlocfilehash: 9205facb5ec4e2491308020d9667a27ab8deb96b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371789"
---
# <a name="receiving-notification-from-common-controls"></a>Ortak Denetimlerden Bildirim Alma

Ortak denetimler, denetimde kullanıcıdan gelen giriş gibi olaylar oluştuğunda üst pencereye bildirim iletileri gönderen alt pencerelerdir.

Uygulama, kullanıcının hangi eylemi yapmak istediğini belirlemek için bu bildirim iletilerine dayanır. En yaygın denetimler bildirim iletilerini WM_NOTIFY iletiolarak gönderir. Windows denetimleri çoğu bildirim iletisini WM_COMMAND iletiolarak gönderir. [CWnd::OnNotify](../mfc/reference/cwnd-class.md#onnotify) WM_NOTIFY iletisinin işleyicisidir. Olduğu `CWnd::OnCommand`gibi , `OnNotify` ileti eşlemlerinde `OnCmdMsg` işlemek için bildirim iletisi gönderir. Bildirimleri işlemek için ileti eşlemi girişi ON_NOTIFY. Daha fazla bilgi için [Teknik Not 61: ON_NOTIFY ve WM_NOTIFY İletileri'ne](../mfc/tn061-on-notify-and-wm-notify-messages.md)bakın.

Alternatif olarak, türetilmiş bir sınıf "ileti yansıması" kullanarak kendi bildirim iletilerini işleyebilir. Daha fazla bilgi için Teknik [Not 62: Windows Denetimleri için İleti Yansıması'na](../mfc/tn062-message-reflection-for-windows-controls.md)bakın.

## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>Bildirim İletisindeki İmleç Konumunu Alma

Zaman zaman, belirli bildirim iletileri ortak bir denetim tarafından alındığı zaman imlecin geçerli konumunu belirlemek yararlıdır. Örneğin, ortak bir denetim NM_RCLICK bir bildirim iletisi aldığında geçerli imleç konumunu belirlemek yararlı olacaktır.

Arayarak `CWnd::GetCurrentMessage`bunu başarmanın basit bir yolu vardır. Ancak, bu yöntem yalnızca iletinin gönderildiği anda imleç konumunu alır. İleti gönderildiğinden beri imleç taşınmış olabileceğinden, `CWnd::GetCursorPos` geçerli imleç konumunu almak için aramanız gerekir.

> [!NOTE]
> `CWnd::GetCurrentMessage`yalnızca ileti işleyicisi içinde çağrılmalıdır.

Bildirim iletisi işleyicisinin gövdesine aşağıdaki kodu ekleyin (bu örnekte, NM_RCLICK):

[!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]

Bu noktada, fare imleci konumu `cursorPos` nesnede depolanır.

## <a name="see-also"></a>Ayrıca bkz.

[Denetimleri Yapma ve Kullanma](../mfc/making-and-using-controls.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
