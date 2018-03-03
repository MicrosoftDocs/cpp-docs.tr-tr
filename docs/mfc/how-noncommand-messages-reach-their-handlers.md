---
title: "Komut dışı iletilerin işleyicilerine erişmesi | Microsoft Docs"
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
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 33d0d65c9916cfc571ecfd623138938c0c883ba5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Komut Dışı İletilerin İşleyicilerine Erişmesi
Komutları, aksine standart Windows iletileri komuta zincirini hedefleri yönlendirilmedi ancak genellikle, Windows ileti gönderdiği pencere tarafından işlenir. Pencerenin ana çerçeve penceresi, bir MDI alt pencere, standart bir denetimde, bir iletişim kutusu, bir görünüm veya başka türde bir alt pencere olabilir.  
  
 Çalışma zamanında her Windows pencereyi bir pencere nesnesi bağlı olduğu (doğrudan veya dolaylı olarak türetilen `CWnd`), kendi ilişkili ileti eşlemesi ve işleyici işlevleri vardır. İleti eşlemesi çerçevesi kullanır — bir komut ettirilmesi — gelen iletileri için işleyiciler eşlemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)

