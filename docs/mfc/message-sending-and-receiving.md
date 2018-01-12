---
title: "İleti gönderme ve alma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows messages [MFC], handling in MFC
- control-notification messages [MFC]
- messages [MFC], receiving
- messages [MFC], MFC
- MFC, messages
- messages [MFC], sending
ms.assetid: 9ce189cb-b259-4c3b-b6f2-9cfbed18b98b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0c587e3b84ae7afd7869a5c1405d8ddc4ab417b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="message-sending-and-receiving"></a>İleti Gönderme ve Alma
İşlem ve framework nasıl yanıt vereceğini gönderen parçası göz önünde bulundurun.  
  
 İletilerin çoğu program ile kullanıcı etkileşimi kaynaklanır. Komutları, fare tıklamaları menü öğesi veya araç çubuğu düğmeleri veya kısayol tuş vuruşları tarafından üretilir. Kullanıcı aynı zamanda Windows iletileri, örneğin, taşıma veya bir pencere yeniden boyutlandırma oluşturur. Windows almak veya odak kaybeder vb. gibi program başlatma veya sonlandırma gibi olaylar meydana geldiğinde, diğer Windows iletileri gönderilir. Denetim bildirimi iletileri fare tıklamaları veya bir iletişim kutusunda düğme veya liste kutusu denetimi gibi bir denetim ile diğer kullanıcı etkileşimleri tarafından üretilir.  
  
 **Çalıştırmak** sınıfının üye işlevini `CWinApp` iletileri alır ve bunları uygun penceresine gönderir. Çoğu komut iletileri uygulamanın ana çerçeve penceresi gönderilir. `WindowProc` İletileri sınıf kitaplığı alır tarafından önceden tanımlanmış ve bunları farklı şekilde, alınan ileti kategoriye göre yönlendirir.  
  
 Şimdi alma işleminin parçası göz önünde bulundurun.  
  
 İletinin ilk alıcı bir pencere nesnesi olmalıdır. Windows iletileri genellikle doğrudan bu pencere nesnesi tarafından işlenir. Komut iletileri, genellikle uygulamanın ana çerçeve penceresinde kaynaklanan yönlendirilen açıklanan komut hedefi zinciri için [komut yönlendirme](../mfc/command-routing.md).  
  
 İletileri veya komutları alabildiğini her nesnenin o çiftleri bir ileti veya kendi işleyicisi adı komutuyla eşleme kendi ileti vardır.  
  
 Bir komut hedefi nesnesi bir ileti veya komut aldığında, bir eşleşme için ileti eşlemesi arar. İleti için bir işleyici bulursa işleyiciyi çağırır. İleti eşlemeleri nasıl aranır hakkında daha fazla bilgi için bkz: [nasıl Framework aramaları ileti eşlemeleri](../mfc/how-the-framework-searches-message-maps.md). Yeniden şekle bakın [Framework komutlarda](../mfc/user-interface-objects-and-command-ids.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)

