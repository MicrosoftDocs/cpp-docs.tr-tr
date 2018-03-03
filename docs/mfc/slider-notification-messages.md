---
title: "Kaydırıcı bildirim iletileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], notifications
- slider controls [MFC], notification messages
- messages, notification
- notifications [MFC], CSliderCtrl
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a4fc9e9065017e04b6375d1e5a8e336d4366755
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="slider-notification-messages"></a>Kaydırıcı Bildirim İletileri
Kaydırıcı denetimi kendi üst penceresi kullanıcı eylemlerinin üst göndererek bildirir `WM_HSCROLL` veya `WM_VSCROLL` kaydırıcı denetimi yönünü bağlı olarak iletileri. Bu iletileri işlemek için işleyicileri eklemek `WM_HSCROLL` ve `WM_VSCROLL` üst pencere iletileri. [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll) ve [OnVScroll](../mfc/reference/cwnd-class.md#onvscroll) üye işlevleri, bir bildirim kodu, kaydırıcıyı ve bir işaretçi konumunu geçirilecektir [CSliderCtrl](../mfc/reference/csliderctrl-class.md) nesnesi. İşaretçi türü olduğuna dikkat edin **CScrollBar \***  işaret olsa bile bir `CSliderCtrl` nesnesi. Kaydırıcı denetimi işlemek gerekiyorsa bu işaretçinin typecast gerekebilir.  
  
 Kaydırma çubuğu bildirim kodları kullanmak yerine kaydırıcı denetimleri farklı bir bildirim kodları kümesini gönderin. Kaydırıcı denetimi gönderir **TB_BOTTOM**, **TB_LINEDOWN**, **TB_LINEUP**, ve **TB_TOP** bildirim kodları yalnızca kullanıcı etkileşim kurduğunda Klavyeyi kullanarak kaydırıcı denetimi ile. **TB_THUMBPOSITION** ve **TB_THUMBTRACK** bildirim iletileri yalnızca kullanıcının fare kullanırken gönderilir. **TB_ENDTRACK**, **TB_PAGEDOWN**, ve **TB_PAGEUP** bildirim kodları, her iki durumda da gönderilir.  
  
 Kaydırıcı denetimi bildirim iletileri ve gönderilecek bildirimler neden olayları (sanal anahtar kodları veya fare olayları) aşağıdaki tabloda listelenmektedir. (Winuser.h standart sanal anahtar kodları listesi için bkz.)  
  
|Bildirim iletisi|Bildirim gönderilmesine neden olan olay|  
|--------------------------|-------------------------------------------|  
|**TB_BOTTOM**|**VK_END**|  
|**TB_ENDTRACK**|`WM_KEYUP`(kullanıcı ilgili sanal anahtar kodu gönderilen bir anahtar yayımlandı)|  
|**TB_LINEDOWN**|**VK_RIGHT** veya **VK_DOWN**|  
|**TB_LINEUP**|**VK_LEFT** veya **VK_UP**|  
|**TB_PAGEDOWN**|**VK_NEXT** (aşağıda veya kaydırıcıyı sağa kanal kullanıcı tıklattınız)|  
|**TB_PAGEUP**|**VK_PRIOR** (yukarıda veya kaydırıcıyı sola kanal kullanıcı tıklattınız)|  
|**TB_THUMBPOSITION**|`WM_LBUTTONUP`Aşağıdaki bir **TB_THUMBTRACK** bildirim iletisi|  
|**TB_THUMBTRACK**|Kaydırıcıyı hareket (kullanıcı kaydırıcıyı sürüklenebilir)|  
|**TB_TOP**|**VK_HOME**|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSliderCtrl kullanma](../mfc/using-csliderctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

