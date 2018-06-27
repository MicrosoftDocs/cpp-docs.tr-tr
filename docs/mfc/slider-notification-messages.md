---
title: Kaydırıcı bildirim iletileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], notifications
- slider controls [MFC], notification messages
- messages, notification
- notifications [MFC], CSliderCtrl
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c383458905d16dda935254e56a5aa9f56a153e83
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956167"
---
# <a name="slider-notification-messages"></a>Kaydırıcı Bildirim İletileri
Kaydırıcı denetimi, kendi üst penceresi kullanıcı eylemlerinin kaydırıcı denetimi yönünü bağlı olarak WM_HSCROLL veya WM_VSCROLL iletileri üst göndererek bildirir. Bu iletileri işlemek için üst penceresine WM_HSCROLL ve WM_VSCROLL iletileri işleyicileri ekleyin. [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll) ve [OnVScroll](../mfc/reference/cwnd-class.md#onvscroll) üye işlevleri, bir bildirim kodu, kaydırıcıyı ve bir işaretçi konumunu geçirilecektir [CSliderCtrl](../mfc/reference/csliderctrl-class.md) nesnesi. İşaretçi türü olduğuna dikkat edin `CScrollBar *` işaret olsa bile bir `CSliderCtrl` nesnesi. Kaydırıcı denetimi işlemek gerekiyorsa bu işaretçinin typecast gerekebilir.  
  
 Kaydırma çubuğu bildirim kodları kullanmak yerine kaydırıcı denetimleri farklı bir bildirim kodları kümesini gönderin. Kaydırıcı denetimi yalnızca klavyeyi kullanarak kullanıcı kaydırıcı denetimi ile etkileşim TB_BOTTOM, TB_LINEDOWN, TB_LINEUP ve TB_TOP bildirim kodları gönderir. Kullanıcının fare kullanırken TB_THUMBPOSITION ve TB_THUMBTRACK bildirim iletileri yalnızca gönderilir. TB_ENDTRACK, TB_PAGEDOWN ve TB_PAGEUP bildirim kodları, her iki durumda da gönderilir.  
  
 Kaydırıcı denetimi bildirim iletileri ve gönderilecek bildirimler neden olayları (sanal anahtar kodları veya fare olayları) aşağıdaki tabloda listelenmektedir. (Winuser.h standart sanal anahtar kodları listesi için bkz.)  
  
|Bildirim iletisi|Bildirim gönderilmesine neden olan olay|  
|--------------------------|-------------------------------------------|  
|TB_BOTTOM|VK_END|  
|TB_ENDTRACK|WM_KEYUP (kullanıcı ilgili sanal anahtar kodu gönderilen bir anahtar yayımlandı)|  
|TB_LINEDOWN|VK_RIGHT veya VK_DOWN|  
|TB_LINEUP|VK_LEFT veya VK_UP|  
|TB_PAGEDOWN|VK_NEXT (aşağıda veya kaydırıcıyı sağa kanal kullanıcı tıklattınız)|  
|TB_PAGEUP|VK_PRIOR (yukarıda veya kaydırıcıyı sola kanal kullanıcı tıklattınız)|  
|TB_THUMBPOSITION|TB_THUMBTRACK bildirim iletiden WM_LBUTTONUP|  
|TB_THUMBTRACK|Kaydırıcıyı hareket (kullanıcı kaydırıcıyı sürüklenebilir)|  
|TB_TOP|VK_HOME|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSliderCtrl kullanma](../mfc/using-csliderctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

