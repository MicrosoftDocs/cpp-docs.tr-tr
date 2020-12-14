---
description: 'Daha fazla bilgi edinin: kaydırıcı bildirim Iletileri'
title: Kaydırıcı Bildirim İletileri
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], notifications
- slider controls [MFC], notification messages
- messages, notification
- notifications [MFC], CSliderCtrl
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
ms.openlocfilehash: fab8d515e71fd2ca8fd390a41b6d1bf68442c24c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216892"
---
# <a name="slider-notification-messages"></a>Kaydırıcı Bildirim İletileri

Kaydırıcı denetimi, kaydırıcı denetiminin yönüne bağlı olarak üst WM_HSCROLL veya WM_VSCROLL iletilerini göndererek Kullanıcı eylemlerinin üst penceresine bildirir. Bu iletileri işlemek için, ana pencereye WM_HSCROLL ve WM_VSCROLL iletileri için işleyiciler ekleyin. [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll) ve [OnVScroll](../mfc/reference/cwnd-class.md#onvscroll) üye işlevlerine bir bildirim kodu, Kaydırıcının konumu ve [CSliderCtrl](../mfc/reference/csliderctrl-class.md) nesnesine yönelik bir işaretçi geçirilecek. Bir nesneye işaret etse de işaretçinin tür olduğunu unutmayın `CScrollBar *` `CSliderCtrl` . Kaydırıcı denetimini değiştirmeniz gerekiyorsa, bu işaretçiye tür atama yapmanız gerekebilir.

Kaydırma çubuğu bildirim kodlarının kullanılması yerine, kaydırıcı denetimleri farklı bir bildirim kodları kümesi gönderir. Kaydırıcı denetimi, yalnızca Kullanıcı klavyeyi kullanarak bir kaydırıcı denetimiyle etkileşime geçtiğinde TB_BOTTOM, TB_LINEDOWN, TB_LINEUP ve TB_TOP bildirim kodlarını gönderir. TB_THUMBPOSITION ve TB_THUMBTRACK bildirim iletileri yalnızca Kullanıcı fareyi kullanırken gönderilir. TB_ENDTRACK, TB_PAGEDOWN ve TB_PAGEUP bildirim kodları her iki durumda da gönderilir.

Aşağıdaki tabloda, bildirimlerin gönderilmesine neden olan kaydırıcı denetimi bildirim iletileri ve Olaylar (sanal anahtar kodları veya fare olayları) listelenmektedir. (Standart sanal anahtar kodlarının listesi için bkz. Winuser. h.)

|Bildirim iletisi|Bildirimin gönderilmesine neden olan olay|
|--------------------------|-------------------------------------------|
|TB_BOTTOM|VK_END|
|TB_ENDTRACK|WM_KEYUP (Kullanıcı ilgili bir sanal anahtar kodu gönderen bir anahtar yayımlamıştır)|
|TB_LINEDOWN|VK_RIGHT veya VK_DOWN|
|TB_LINEUP|VK_LEFT veya VK_UP|
|TB_PAGEDOWN|VK_NEXT (Kullanıcı kaydırıcının sağ veya sağ tarafındaki kanala tıkladı)|
|TB_PAGEUP|VK_PRIOR (Kullanıcı kaydırıcının solundaki veya solundaki kanala tıkladı)|
|TB_THUMBPOSITION|TB_THUMBTRACK bildirim iletisini izleyen WM_LBUTTONUP|
|TB_THUMBTRACK|Kaydırıcı hareketi (Kullanıcı kaydırıcıyı sürüklemiş)|
|TB_TOP|VK_HOME|

## <a name="see-also"></a>Ayrıca bkz.

[CSliderCtrl Kullanma](../mfc/using-csliderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
