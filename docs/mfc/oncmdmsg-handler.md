---
title: OnCmdMsg işleyicisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OnCmdMsg
dev_langs:
- C++
helpviewer_keywords:
- messages, routing
- handlers [MFC]
- command routing [MFC], OnCmdMsg handler
- handlers, OnCmdMessage [MFC]
- OnCmdMessage method [MFC]
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0657b05619a966ed171630d00adcd9303af7e18b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="oncmdmsg-handler"></a>OnCmdMsg İşleyicisi
Komut yönlendirme gerçekleştirmek için her komut hedefi çağırır `OnCmdMsg` dizisindeki sonraki komut hedefinin üye işlevi. Komutu kullanım hedefler `OnCmdMsg` bunlar bir komut işlenip işlenmeyeceğini belirler ve yönlendirmek için başka bir komut hedefinin bunlar yürütemiyorsa.  
  
 Her komut hedefi sınıfı geçersiz kılabilir `OnCmdMsg` üye işlevi. Geçersiz kılmalar her sınıf rota komutları belirli bir sonraki hedef sağlar. Bir çerçeve penceresinde, örneğin, her zaman komutları, geçerli alt pencere veya görünümü, tabloda gösterilen yönlendirir [standart komut rota](../mfc/command-routing.md).  
  
 Varsayılan `CCmdTarget` uyarlamasını `OnCmdMsg` aldığı her komut iletisi için bir işleyici işlevi aramak için ileti eşlemesi komutu hedef sınıfın kullanır — aynı şekilde standart iletilerini aranır. Bir eşleşme bulursa işleyiciyi çağırır. İleti eşleme arama açıklanmıştır içinde [nasıl Framework aramaları ileti eşlemeleri](../mfc/how-the-framework-searches-message-maps.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)

