---
title: Komut Dışı İletilerin İşleyicilerine Erişmesi
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
ms.openlocfilehash: 4b9fb0a72b330380f0207db9968199a7e4c3d9b3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295064"
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Komut Dışı İletilerin İşleyicilerine Erişmesi

Komutlarından farklı olarak standart Windows iletileri bir komuta zincirini hedefleri yönlendirilir değil, ancak genellikle, Windows iletinin gönderdiği pencere tarafından işlenir. Pencere, bir ana çerçeve penceresi, MDI alt penceresi, standart bir denetimde, bir iletişim kutusu, bir görünüm veya başka türde bir alt pencere olabilir.

Çalışma zamanında, her Windows penceresi bir pencere nesnesi için bağlı (doğrudan veya dolaylı olarak türetilmiş `CWnd`) kendi ilişkili ileti eşlemesi ve işleyici işlevlerine sahip. Çerçeve ileti eşlemesi kullanır; bir komut için — gelen iletileri için işleyiciler eşlemek için.

## <a name="see-also"></a>Ayrıca bkz.

[Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)
