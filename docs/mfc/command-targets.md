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
ms.openlocfilehash: 1cbcfa1042a8430c704bad93e4bc0ce5655b5921
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="command-targets"></a>Komut Hedefleri
Şekil [Framework komutlarda](../mfc/user-interface-objects-and-command-ids.md) menü öğesi ve framework çağrılarını nesne tıklatıldığında elde edilen komutu yürütmek için işleyici işlevi gibi bir kullanıcı arabirimi nesnesi arasındaki bağlantıyı gösterir.  
  
 Windows komut iletileri doğrudan, ileti işleyicisi sonra adlı bir pencere için olmayan iletiler gönderir. Ancak, framework adayı nesne sayısı için komutları yönlendirir — "komut hedefleri" olarak adlandırılan — biri normalde çağırır komutu için bir işleyici. İşleyici işlevleri komutlar ve standart Windows iletileri için aynı şekilde çalışır, ancak tarafından bunlar denir mekanizmaları açıklandığı gibi farklı [Framework bir işleyici çağırması](../mfc/how-the-framework-calls-a-handler.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)

