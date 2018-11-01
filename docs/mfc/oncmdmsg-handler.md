---
title: OnCmdMsg İşleyicisi
ms.date: 11/04/2016
f1_keywords:
- OnCmdMsg
helpviewer_keywords:
- messages, routing
- handlers [MFC]
- command routing [MFC], OnCmdMsg handler
- handlers, OnCmdMessage [MFC]
- OnCmdMessage method [MFC]
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
ms.openlocfilehash: 37b3d5ffa3e6492c8c00b8b22eba58d09fad51f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643176"
---
# <a name="oncmdmsg-handler"></a>OnCmdMsg İşleyicisi

Komut yönlendirme gerçekleştirmek için her komut hedefi çağırır `OnCmdMsg` dizideki sonraki komut hedefinin bir üye işlevi. Komut hedefleyen kullanım `OnCmdMsg` komut başa çıkabilir olup olmadığını belirlemek için ve yönlendirmek için başka bir komut hedefinin bunlar yürütemiyorsa.

Her komut hedefi sınıfı geçersiz kılabilir `OnCmdMsg` üye işlevi. Geçersiz kılmalar, her sınıf rota komutları belirli bir sonraki hedefe olanak tanır. Çerçeve penceresi, örneğin, her zaman komutları, geçerli bir alt pencere ya da görünümü tabloda gösterildiği gibi yönlendirir [standart komut yönlendirme](../mfc/command-routing.md).

Varsayılan `CCmdTarget` uygulaması `OnCmdMsg` aldığı her komut iletisi için bir işleyici işlevi aramak için komut hedef sınıfın ileti eşlemesi kullanır; aynı şekilde standart iletileri aranır. Bu bir eşleşme bulunursa, işleyici çağırır. İleti eşleme arama bölümünde açıklanmıştır [nasıl Framework arar ileti eşlemeleri](../mfc/how-the-framework-searches-message-maps.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)

