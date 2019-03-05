---
title: Kaydırıcı Bildirim İletileri
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], notifications
- slider controls [MFC], notification messages
- messages, notification
- notifications [MFC], CSliderCtrl
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
ms.openlocfilehash: bee2d602512ea1a6af39b0bb218ee7333b399c80
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294245"
---
# <a name="slider-notification-messages"></a>Kaydırıcı Bildirim İletileri

Bir kaydırıcı denetimi, üst kaydırıcı denetiminin yönünü bağlı olarak WM_HSCROLL veya WM_VSCROLL iletiler göndererek kullanıcı eylemlerinin kendi üst penceresine bildirir. Bu iletileri işleyen ana pencerenin WM_HSCROLL ve WM_VSCROLL iletileri için işleyiciler ekleyin. [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll) ve [OnVScroll](../mfc/reference/cwnd-class.md#onvscroll) üye işlevleri, bir bildirim kodu, kaydırıcıyı ve işaretçisi konumunu geçirilir [CSliderCtrl](../mfc/reference/csliderctrl-class.md) nesne. İşaretçi türü olduğuna dikkat edin `CScrollBar *` işaret olsa bile bir `CSliderCtrl` nesne. Kaydırıcı denetimi işlemek gerekiyorsa bu işaretçinin türü atayarak gerekebilir.

Kaydırıcı denetimleri kaydırma çubuğu bildirim kodları kullanmak yerine, farklı bir bildirim kodları kümesi gönderin. Yalnızca klavyeyi kullanarak kullanıcı bir kaydırıcı denetimi ile etkileşim kurduğunda bir kaydırıcı denetimi TB_BOTTOM, TB_LINEDOWN TB_LINEUP ve TB_TOP bildirim kodları gönderir. Kullanıcı fare kullanılırken TB_THUMBPOSITION ve TB_THUMBTRACK bildirim iletileri yalnızca gönderilir. Her iki durumda da TB_ENDTRACK TB_PAGEDOWN ve TB_PAGEUP bildirim kodları gönderilir.

Kaydırıcı denetimi bildirim iletileri ve bildirimleri gönderilmesini neden olayları (sanal anahtar kodlarını veya fare olayları) aşağıdaki tabloda listelenmektedir. (Winuser.h standart sanal anahtar kodlarının listesi için bkz.)

|Bildirim iletisi|Bildirim gönderilecek neden olay|
|--------------------------|-------------------------------------------|
|TB_BOTTOM|VK_END|
|TB_ENDTRACK|WM_KEYUP (kullanıcının ilgili bir sanal anahtar kodu gönderilen bir tuş serbest)|
|TB_LINEDOWN|VK_RIGHT veya VK_DOWN|
|TB_LINEUP|VK_LEFT veya VK_UP|
|TB_PAGEDOWN|VK_NEXT (aşağıda veya kaydırıcının sağa kanalı kullanıcı tıklandığında)|
|TB_PAGEUP|VK_PRIOR (yukarıda veya sol kaydırıcının kanal kullanıcı tıklandığında)|
|TB_THUMBPOSITION|TB_THUMBTRACK bildirim sonraki WM_LBUTTONUP|
|TB_THUMBTRACK|(Kullanıcı, kaydırıcı sürüklenebilir) kaydırıcı taşıma|
|TB_TOP|VK_HOME|

## <a name="see-also"></a>Ayrıca bkz.

[CSliderCtrl Kullanma](../mfc/using-csliderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
