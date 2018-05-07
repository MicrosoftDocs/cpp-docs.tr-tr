---
title: Komut dışı iletilerin işleyicilerine erişmesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3999c74bf7a612acb998e7a044c12948d7679d9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Komut Dışı İletilerin İşleyicilerine Erişmesi
Komutları, aksine standart Windows iletileri komuta zincirini hedefleri yönlendirilmedi ancak genellikle, Windows ileti gönderdiği pencere tarafından işlenir. Pencerenin ana çerçeve penceresi, bir MDI alt pencere, standart bir denetimde, bir iletişim kutusu, bir görünüm veya başka türde bir alt pencere olabilir.  
  
 Çalışma zamanında her Windows pencereyi bir pencere nesnesi bağlı olduğu (doğrudan veya dolaylı olarak türetilen `CWnd`), kendi ilişkili ileti eşlemesi ve işleyici işlevleri vardır. İleti eşlemesi çerçevesi kullanır — bir komut ettirilmesi — gelen iletileri için işleyiciler eşlemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)

