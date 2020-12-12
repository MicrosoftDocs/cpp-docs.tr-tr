---
description: 'Hakkında daha fazla bilgi edinin: komut olmayan Iletilerin Işleyicilerine ulaşma şekli'
title: Komut Dışı İletilerin İşleyicilerine Erişmesi
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
ms.openlocfilehash: e337a62a731e7ed0832b6cd28d1f56024247c176
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172823"
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Komut Dışı İletilerin İşleyicilerine Erişmesi

Komutların aksine, standart Windows iletileri bir komut hedefi zinciri aracılığıyla yönlendirilemez, ancak genellikle Windows 'un iletiyi gönderdiği pencere tarafından işlenir. Pencere, bir ana çerçeve penceresi, bir MDI alt penceresi, standart denetim, iletişim kutusu, görünüm veya başka bir alt pencere türü olabilir.

Çalışma zamanında, her Windows penceresi, `CWnd` kendi ilişkili ileti eşlemesi ve işleyici işlevleri olan bir pencere nesnesine (doğrudan veya dolaylı olarak türetilmiş) eklenir. Çerçeve, gelen iletileri işleyicilere eşlemek için ileti haritasını (bir komut gibi) kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve bir Işleyiciyi nasıl çağırır](how-the-framework-calls-a-handler.md)
