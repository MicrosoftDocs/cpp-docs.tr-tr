---
title: Komut dışı iletilerin işleyicilerine erişmesi nasıl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b5c38a1d4294993170cfeff64be6a83700fa7497
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373444"
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Komut Dışı İletilerin İşleyicilerine Erişmesi

Komutlarından farklı olarak standart Windows iletileri bir komuta zincirini hedefleri yönlendirilir değil, ancak genellikle, Windows iletinin gönderdiği pencere tarafından işlenir. Pencere, bir ana çerçeve penceresi, MDI alt penceresi, standart bir denetimde, bir iletişim kutusu, bir görünüm veya başka türde bir alt pencere olabilir.

Çalışma zamanında, her Windows penceresi bir pencere nesnesi için bağlı (doğrudan veya dolaylı olarak türetilmiş `CWnd`) kendi ilişkili ileti eşlemesi ve işleyici işlevlerine sahip. Çerçeve ileti eşlemesi kullanır; bir komut için — gelen iletileri için işleyiciler eşlemek için.

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)

