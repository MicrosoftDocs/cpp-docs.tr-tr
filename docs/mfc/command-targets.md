---
title: Komut Hedefleri
ms.date: 11/04/2016
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
ms.openlocfilehash: 3f3305e7b67f4c001861c79c76c3b43a0c5a8ef0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506891"
---
# <a name="command-targets"></a>Komut Hedefleri

Şekil [Framework komutlarında](../mfc/user-interface-objects-and-command-ids.md) menü öğesi ve framework nesnesine tıklandığında ortaya çıkan komutu yürütmek için çağırdığı işleyici işlevi gibi bir kullanıcı arabirimi nesnesi arasındaki bağlantıyı gösterir.

Windows komut iletiler, ileti işleyicisi sonra çağrılır olarak doğrudan bir pencere için iletileri gönderir. Ancak, framework aday nesnelerin bir sayıya komutları yönlendirir — "komut hedefleri" adlı — biri normalde çağırır komutu için bir işleyici. İşleyici işlevleri komutları hem standart Windows iletileri aynı şekilde çalışır, ancak açıklandığı gibi bunlar çağrılır mekanizmaları farklı [Framework'ün işleyici çağırması](../mfc/how-the-framework-calls-a-handler.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)

