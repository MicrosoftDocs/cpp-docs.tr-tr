---
title: "Standart komut yönlendirmeyi geçersiz kılma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7168236ea315d42961f984a3c4f94845cd8398df
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="overriding-the-standard-command-routing"></a>Standart Komut Yönlendirmeyi Geçersiz Kılma
Standart framework yönlendirme bazı değişim uyguladığınızda gerekir nadir durumlarda, bunu geçersiz kılabilirsiniz. Geçersiz kılarak bir veya daha fazla sınıflarda yönlendirme değiştirmek için fikirdir `OnCmdMsg` bu sınıfların. Bunu yapın:  
  
-   Sınıfında, varsayılan olmayan nesne için geçirmek için sipariş keser.  
  
-   Yeni varsayılan olmayan nesne veya komut hedefleri komutları sırayla geçirebilirsiniz.  
  
 Yönlendirme içine yeni bir nesne eklerseniz, kendi sınıfı komutu hedef sınıf olmalıdır. Geçersiz kılma sürümlerinde `OnCmdMsg`, geçersiz kılma sürüm çağırdığınızdan emin olun. Bkz: [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) sınıfının üye işlevini `CCmdTarget` içinde *MFC başvurusu* ve bu tür sınıflar sürümlerde `CView` ve **CDocument** içinde Sağlanan kaynak kodu örnekleri için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework bir işleyici çağırması](../mfc/how-the-framework-calls-a-handler.md)

