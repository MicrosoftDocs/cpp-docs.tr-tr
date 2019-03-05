---
title: Komut Hedefleri
ms.date: 11/04/2016
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
ms.openlocfilehash: ed3d6a68967dc7f4244f887ae34760fdb99fa7f5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274464"
---
# <a name="command-targets"></a>Komut Hedefleri

Şekil [Framework komutlarında](../mfc/user-interface-objects-and-command-ids.md) menü öğesi ve framework nesnesine tıklandığında ortaya çıkan komutu yürütmek için çağırdığı işleyici işlevi gibi bir kullanıcı arabirimi nesnesi arasındaki bağlantıyı gösterir.

Windows komut iletiler, ileti işleyicisi sonra çağrılır olarak doğrudan bir pencere için iletileri gönderir. Ancak, framework aday nesnelerin bir sayıya komutları yönlendirir — "komut hedefleri" adlı — biri normalde çağırır komutu için bir işleyici. İşleyici işlevleri komutları hem standart Windows iletileri aynı şekilde çalışır, ancak açıklandığı gibi bunlar çağrılır mekanizmaları farklı [Framework'ün işleyici çağırması](../mfc/how-the-framework-calls-a-handler.md).

## <a name="see-also"></a>Ayrıca bkz.

[Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)
