---
title: Animasyon Denetimlerinin Gönderdiği Bildirimler
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
ms.openlocfilehash: e9e5b94736de44d5cfeef81f5b78a759df3b8aa0
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619904"
---
# <a name="notifications-sent-by-animation-controls"></a>Animasyon Denetimlerinin Gönderdiği Bildirimler

Animasyon denetimi ([CAnimateCtrl](reference/canimatectrl-class.md)) iki farklı tür bildirim iletisi gönderir. Bildirimler [WM_COMMAND](/windows/win32/menurc/wm-command) iletileri biçiminde gönderilir.

[Acn_start](/windows/win32/Controls/acn-start) ileti, animasyon denetimi bir klibi yürütmeye başladığında gönderilir. [ACN_STOP](/windows/win32/Controls/acn-stop) ileti, animasyon denetimi bir klibi yürütmeyi bitirdiğinde veya durdurulduğunda gönderilir.

## <a name="see-also"></a>Ayrıca bkz.

[CAnimateCtrl Kullanma](using-canimatectrl.md)<br/>
[Denetimler](controls-mfc.md)
