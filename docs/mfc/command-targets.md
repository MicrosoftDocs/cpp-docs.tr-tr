---
title: Komut Hedefleri
ms.date: 11/04/2016
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
ms.openlocfilehash: 59ba197174e95e42cd237c875f39f07801cb3dbe
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619306"
---
# <a name="command-targets"></a>Komut Hedefleri

Çerçevesindeki şekil [komutları](user-interface-objects-and-command-ids.md) , bir menü öğesi gibi bir kullanıcı arabirimi nesnesi ile nesnenin tıklandığı zaman elde edilen komutu yürütmek için çağırdığı işleyici işlevi arasındaki bağlantıyı gösterir.

Windows, komut iletileri olmayan iletileri doğrudan ileti işleyicisi olan bir pencereye gönderir. Ancak Framework, komutları genellikle komut için bir işleyici çağıran bir dizi aday nesnesine ("komut hedefleri" adı verilir) yönlendirir. İşleyici işlevleri, hem komutlar hem de standart Windows iletileri için aynı şekilde çalışır, ancak çağrıldıkları mekanizmalar, [Framework 'ün bir Işleyiciyi nasıl çağırdığı konusunda](how-the-framework-calls-a-handler.md)açıklandığı gibi farklı olur.

## <a name="see-also"></a>Ayrıca bkz.

[Framework'teki İletiler ve Komutlar](messages-and-commands-in-the-framework.md)
