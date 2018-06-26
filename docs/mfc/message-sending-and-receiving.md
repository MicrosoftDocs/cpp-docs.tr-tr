---
title: İleti gönderme ve alma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [MFC], handling in MFC
- control-notification messages [MFC]
- messages [MFC], receiving
- messages [MFC], MFC
- MFC, messages
- messages [MFC], sending
ms.assetid: 9ce189cb-b259-4c3b-b6f2-9cfbed18b98b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55f450085c446503ebf86960dbee1b0d930691c2
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932010"
---
# <a name="message-sending-and-receiving"></a>İleti Gönderme ve Alma
İşlem ve framework nasıl yanıt vereceğini gönderen parçası göz önünde bulundurun.  
  
 İletilerin çoğu program ile kullanıcı etkileşimi kaynaklanır. Komutları, fare tıklamaları menü öğesi veya araç çubuğu düğmeleri veya kısayol tuş vuruşları tarafından üretilir. Kullanıcı aynı zamanda Windows iletileri, örneğin, taşıma veya bir pencere yeniden boyutlandırma oluşturur. Windows almak veya odak kaybeder vb. gibi program başlatma veya sonlandırma gibi olaylar meydana geldiğinde, diğer Windows iletileri gönderilir. Denetim bildirimi iletileri fare tıklamaları veya bir iletişim kutusunda düğme veya liste kutusu denetimi gibi bir denetim ile diğer kullanıcı etkileşimleri tarafından üretilir.  
  
 `Run` Sınıfının üye işlevini `CWinApp` iletileri alır ve bunları uygun penceresine gönderir. Çoğu komut iletileri uygulamanın ana çerçeve penceresi gönderilir. `WindowProc` İletileri sınıf kitaplığı alır tarafından önceden tanımlanmış ve bunları farklı şekilde, alınan ileti kategoriye göre yönlendirir.  
  
 Şimdi alma işleminin parçası göz önünde bulundurun.  
  
 İletinin ilk alıcı bir pencere nesnesi olmalıdır. Windows iletileri genellikle doğrudan bu pencere nesnesi tarafından işlenir. Komut iletileri, genellikle uygulamanın ana çerçeve penceresinde kaynaklanan yönlendirilen açıklanan komut hedefi zinciri için [komut yönlendirme](../mfc/command-routing.md).  
  
 İletileri veya komutları alabildiğini her nesnenin o çiftleri bir ileti veya kendi işleyicisi adı komutuyla eşleme kendi ileti vardır.  
  
 Bir komut hedefi nesnesi bir ileti veya komut aldığında, bir eşleşme için ileti eşlemesi arar. İleti için bir işleyici bulursa işleyiciyi çağırır. İleti eşlemeleri nasıl aranır hakkında daha fazla bilgi için bkz: [nasıl Framework aramaları ileti eşlemeleri](../mfc/how-the-framework-searches-message-maps.md). Yeniden şekle bakın [Framework komutlarda](../mfc/user-interface-objects-and-command-ids.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)

