---
title: "Komut dışı iletilerin işleyicilerine erişmesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0e6a6f30597ddb5ea68b3a5a00c35e27024fb9b0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Komut Dışı İletilerin İşleyicilerine Erişmesi
Komutları, aksine standart Windows iletileri komuta zincirini hedefleri yönlendirilmedi ancak genellikle, Windows ileti gönderdiği pencere tarafından işlenir. Pencerenin ana çerçeve penceresi, bir MDI alt pencere, standart bir denetimde, bir iletişim kutusu, bir görünüm veya başka türde bir alt pencere olabilir.  
  
 Çalışma zamanında her Windows pencereyi bir pencere nesnesi bağlı olduğu (doğrudan veya dolaylı olarak türetilen `CWnd`), kendi ilişkili ileti eşlemesi ve işleyici işlevleri vardır. İleti eşlemesi çerçevesi kullanır — bir komut ettirilmesi — gelen iletileri için işleyiciler eşlemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework bir işleyici çağırması](../mfc/how-the-framework-calls-a-handler.md)

