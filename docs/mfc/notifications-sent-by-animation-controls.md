---
title: Animasyon denetimlerinin gönderdiği bildirimler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb83fe6195c01c1e9dbcc2c00e43738af9ebc8e2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386398"
---
# <a name="notifications-sent-by-animation-controls"></a>Animasyon Denetimlerinin Gönderdiği Bildirimler

Animasyon denetimi ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) iki farklı türde bildirim iletileri gönderir. Bildirimler biçiminde gönderilir [WM_COMMAND](/windows/desktop/menurc/wm-command) iletileri.

[ACN_START](/windows/desktop/Controls/acn-start) animasyon denetimi bir klibi yürütmeye başladığında ileti gönderilir. [ACN_STOP](/windows/desktop/Controls/acn-stop) animasyon denetimi tamamlandı veya bir klibi yürütmeye durduruldu olduğunda ileti gönderilir.

## <a name="see-also"></a>Ayrıca Bkz.

[CAnimateCtrl Kullanma](../mfc/using-canimatectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

