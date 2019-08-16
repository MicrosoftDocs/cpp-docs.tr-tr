---
title: Animasyon Denetimlerinin Gönderdiği Bildirimler
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
ms.openlocfilehash: 68ede3bc55669a29eef192d38b29b8c1ab433e4b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508026"
---
# <a name="notifications-sent-by-animation-controls"></a>Animasyon Denetimlerinin Gönderdiği Bildirimler

Animasyon denetimi ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) iki farklı tür bildirim iletisi gönderir. Bildirimler [WM_COMMAND](/windows/win32/menurc/wm-command) iletileri biçiminde gönderilir.

[Acn_start](/windows/win32/Controls/acn-start) iletisi, animasyon denetimi bir klibi yürütmeye başladığında gönderilir. [ACN_STOP](/windows/win32/Controls/acn-stop) iletisi, animasyon denetimi bir klibi yürütmeyi bitirdiğinde veya durdurulduğunda gönderilir.

## <a name="see-also"></a>Ayrıca bkz.

[CAnimateCtrl Kullanma](../mfc/using-canimatectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
