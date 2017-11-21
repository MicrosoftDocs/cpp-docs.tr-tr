---
title: "Üye işlevini çalıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bf874dc0d5b2ec8d814bd59a0cfd7fedab3370c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="run-member-function"></a>Üye İşlevini Çalıştırma
Framework uygulamanın kendi zamanı çoğunu geçirdiği [çalıştırmak](../mfc/reference/cwinapp-class.md#run) sınıfının üye işlevini [CWinApp](../mfc/reference/cwinapp-class.md). Başlatma sonra `WinMain` çağrıları **çalıştırmak** ileti döngüsü işlenemiyor.  
  
 **Çalıştırma** kullanılabilir iletiler için ileti sırası denetimi bir ileti döngüsü arasında geçiş yapar. Bir ileti olup olmadığını **çalıştırmak** eylemi için gönderir. Hiçbir ileti varsa, hangi doğruysa genellikle **çalıştırmak** çağrıları `OnIdle` Bitti, veya framework gereken boşta kalma süresi işlem yapmadan yapmak için. Hiçbir iletiler ve boşta hiçbir işlem yapmak için varsa, uygulamanın bir şey kadar bekler. Uygulama sonlandırıldığında **çalıştırmak** çağrıları `ExitInstance`. Şekil [ONIDLE üye işlevi](../mfc/onidle-member-function.md) ileti döngüde eylemlerin sırasını gösterir.  
  
 İleti gönderilirken ileti türüne bağlıdır. Daha fazla bilgi için bkz: [iletiler ve komutlar Framework'te](../mfc/messages-and-commands-in-the-framework.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinApp: Uygulama sınıfı](../mfc/cwinapp-the-application-class.md)
