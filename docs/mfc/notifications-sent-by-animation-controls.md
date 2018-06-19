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
ms.openlocfilehash: c1696389ce3dc40c5d02ec660ebaeb6bf3e6c3ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345259"
---
# <a name="notifications-sent-by-animation-controls"></a>Animasyon Denetimlerinin Gönderdiği Bildirimler
Animasyon denetimi ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) iki farklı türde bildirim iletileri gönderir. Bildirimler biçiminde gönderilir [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) iletileri.  
  
 [ACN_START](http://msdn.microsoft.com/library/windows/desktop/bb761891) animasyon denetimi küçük çalma başlatıldığında ileti gönderilir. [ACN_STOP](http://msdn.microsoft.com/library/windows/desktop/bb761893) iletinin gönderildiği animasyon denetimi tamamlandı veya küçük yürütme durduruldu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAnimateCtrl kullanma](../mfc/using-canimatectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

