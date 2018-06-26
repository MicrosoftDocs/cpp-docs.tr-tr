---
title: Standart komut yönlendirmeyi geçersiz kılma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58156f6d1c361c24dc6cf04a9208157d614f91a8
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929016"
---
# <a name="overriding-the-standard-command-routing"></a>Standart Komut Yönlendirmeyi Geçersiz Kılma
Standart framework yönlendirme bazı değişim uyguladığınızda gerekir nadir durumlarda, bunu geçersiz kılabilirsiniz. Geçersiz kılarak bir veya daha fazla sınıflarda yönlendirme değiştirmek için fikirdir `OnCmdMsg` bu sınıfların. Bunu yapın:  
  
-   Sınıfında, varsayılan olmayan nesne için geçirmek için sipariş keser.  
  
-   Yeni varsayılan olmayan nesne veya komut hedefleri komutları sırayla geçirebilirsiniz.  
  
 Yönlendirme içine yeni bir nesne eklerseniz, kendi sınıfı komutu hedef sınıf olmalıdır. Geçersiz kılma sürümlerinde `OnCmdMsg`, geçersiz kılma sürüm çağırdığınızdan emin olun. Bkz: [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) sınıfının üye işlevini `CCmdTarget` içinde *MFC başvurusu* ve bu tür sınıflar sürümlerde `CView` ve `CDocument` örnekleri için sağlanan kaynak kodu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)

