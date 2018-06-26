---
title: Üye işlevini çalıştırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a658af47723a9c19218b205a17cb46919d7abd59
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932292"
---
# <a name="run-member-function"></a>Üye İşlevini Çalıştırma
Framework uygulamanın kendi zamanı çoğunu geçirdiği [çalıştırmak](../mfc/reference/cwinapp-class.md#run) sınıfının üye işlevini [CWinApp](../mfc/reference/cwinapp-class.md). Başlatma sonra `WinMain` çağrıları `Run` ileti döngüsü işlenemiyor.  
  
 `Run` ileti sırası kullanılabilir iletiler için denetimi bir ileti döngüsü arasında geçiş yapar. Bir ileti olup olmadığını `Run` için eylem gönderir. Hiçbir ileti varsa, hangi doğruysa genellikle `Run` çağrıları `OnIdle` Bitti, veya framework gereken boşta kalma süresi işlem yapmadan yapmak için. Hiçbir iletiler ve boşta hiçbir işlem yapmak için varsa, uygulamanın bir şey kadar bekler. Uygulama sonlandırıldığında `Run` çağrıları `ExitInstance`. Şekil [ONIDLE üye işlevi](../mfc/onidle-member-function.md) ileti döngüde eylemlerin sırasını gösterir.  
  
 İleti gönderilirken ileti türüne bağlıdır. Daha fazla bilgi için bkz: [iletiler ve komutlar Framework'te](../mfc/messages-and-commands-in-the-framework.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
