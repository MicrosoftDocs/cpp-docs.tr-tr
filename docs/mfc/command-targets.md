---
title: Komut hedefleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 408f63b80ff30a7ebdc51e5becb1dd97bb062852
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404234"
---
# <a name="command-targets"></a>Komut Hedefleri

Şekil [Framework komutlarında](../mfc/user-interface-objects-and-command-ids.md) menü öğesi ve framework nesnesine tıklandığında ortaya çıkan komutu yürütmek için çağırdığı işleyici işlevi gibi bir kullanıcı arabirimi nesnesi arasındaki bağlantıyı gösterir.

Windows komut iletiler, ileti işleyicisi sonra çağrılır olarak doğrudan bir pencere için iletileri gönderir. Ancak, framework aday nesnelerin bir sayıya komutları yönlendirir — "komut hedefleri" adlı — biri normalde çağırır komutu için bir işleyici. İşleyici işlevleri komutları hem standart Windows iletileri aynı şekilde çalışır, ancak açıklandığı gibi bunlar çağrılır mekanizmaları farklı [Framework'ün işleyici çağırması](../mfc/how-the-framework-calls-a-handler.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)

