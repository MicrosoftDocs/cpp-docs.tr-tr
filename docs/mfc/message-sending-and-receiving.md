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
ms.openlocfilehash: e28f35fc87b78ac4e04df0f8147d76571c51320e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438827"
---
# <a name="message-sending-and-receiving"></a>İleti Gönderme ve Alma

İşlem ve framework nasıl yanıt vereceğini gönderen parçası göz önünde bulundurun.

İletilerin çoğu program ile kullanıcı etkileşimi sonucunda. Komutları kısayol tuş vuruşlarını veya fare tıklamaları menü öğeleri ya da araç çubuğu düğmeleri tarafından oluşturulur. Kullanıcı aynı zamanda Windows iletileri, örneğin, taşıma veya yeniden boyutlandırma bir pencere oluşturur. Windows alın veya odağı kaybeder ve benzeri gibi program başlatma veya sonlandırma gibi olaylar meydana geldiğinde, diğer Windows iletileri gönderilir. Denetim bildirimi iletileri fare tıklamalarına veya diğer kullanıcı etkileşim iletişim kutusunda bir düğme veya liste kutusu denetimi gibi bir denetim tarafından oluşturulur.

`Run` Sınıfının üye işlevinde `CWinApp` iletileri alır ve bunları uygun penceresine gönderir. Çoğu komut iletileri, uygulamanın ana çerçeve penceresine gönderilir. `WindowProc` İletileri sınıf kitaplığı Alınanlar tarafından önceden tanımlanmış ve bunları alınan ileti kategorisine bağlı olarak farklı şekilde yönlendirir.

Alma işleminin parçası göz önünde bulundurun.

İlk ileti alıcısı, pencere nesnesi olması gerekir. Windows iletileri, genellikle doğrudan bu pencere nesnesi tarafından işlenir. Komut iletileri, genellikle uygulamanın ana çerçeve penceresine kaynaklanan açıklanan hedef komut zinciri yönlendirilen [komut yönlendirme](../mfc/command-routing.md).

İletileri veya komutları alabildiğini her nesne bir ileti veya kendi işleyicisi adı ile komutu bu çiftleri harita kendi ileti vardır.

Komut-hedef nesne ileti veya komutunu aldığında, kendi ileti eşlemesi için bir eşleşme arar. İleti için bir işleyici bulursa, işleyici çağırır. İleti eşlemeleri nasıl aranır hakkında daha fazla bilgi için bkz. [nasıl Framework arar ileti eşlemeleri](../mfc/how-the-framework-searches-message-maps.md). Yeniden şekle başvuruda [Framework komutlarında](../mfc/user-interface-objects-and-command-ids.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)

