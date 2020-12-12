---
description: 'Şu konuda daha fazla bilgi edinin: komut hedefleri'
title: Komut Hedefleri
ms.date: 11/04/2016
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
ms.openlocfilehash: b7be03282400c2d3a0dcf5eb0d24a0b06456ebca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206259"
---
# <a name="command-targets"></a>Komut Hedefleri

Çerçevesindeki şekil [komutları](user-interface-objects-and-command-ids.md) , bir menü öğesi gibi bir kullanıcı arabirimi nesnesi ile nesnenin tıklandığı zaman elde edilen komutu yürütmek için çağırdığı işleyici işlevi arasındaki bağlantıyı gösterir.

Windows, komut iletileri olmayan iletileri doğrudan ileti işleyicisi olan bir pencereye gönderir. Ancak Framework, komutları genellikle komut için bir işleyici çağıran bir dizi aday nesnesine ("komut hedefleri" adı verilir) yönlendirir. İşleyici işlevleri, hem komutlar hem de standart Windows iletileri için aynı şekilde çalışır, ancak çağrıldıkları mekanizmalar, [Framework 'ün bir Işleyiciyi nasıl çağırdığı konusunda](how-the-framework-calls-a-handler.md)açıklandığı gibi farklı olur.

## <a name="see-also"></a>Ayrıca bkz.

[Çerçevede iletiler ve komutlar](messages-and-commands-in-the-framework.md)
