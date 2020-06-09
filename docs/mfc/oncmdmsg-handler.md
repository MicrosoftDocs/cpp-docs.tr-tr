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
ms.openlocfilehash: 5114fe53a5bac345eb6a55fb6c371f7bc1f698ef
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624023"
---
# <a name="oncmdmsg-handler"></a>OnCmdMsg İşleyicisi

Komutların yönlendirilmesini başarmak için, her komut hedefi `OnCmdMsg` dizideki bir sonraki komut hedefinin üye işlevini çağırır. Komut hedefleri, `OnCmdMsg` bir komutu işleyebilecekleri ve işleyememesi durumunda onu başka bir komut hedefine yönlendirip işleyemeyeceğini belirlemede kullanır.

Her komut hedefi sınıfı üye işlevini geçersiz kılabilir `OnCmdMsg` . Geçersiz kılmalar her bir sınıfın komut için belirli bir sonraki hedefe yol almasına izin verir. Örneğin, bir çerçeve penceresi, her zaman komutları geçerli alt penceresine veya görünümüne, tablo [standart komut rotasında](command-routing.md)gösterildiği gibi yönlendirir.

Varsayılan `CCmdTarget` uygulama, `OnCmdMsg` aldığı her komut iletisi için bir işleyici işlevi aramak üzere komut-hedef sınıfının ileti eşlemesini kullanır ve standart mesajların aranacağı şekilde. Bir eşleşme bulunursa işleyiciyi çağırır. İleti eşleme araması [, Framework 'Ün Ileti eşlemelerini arayacağı](how-the-framework-searches-message-maps.md)şekilde açıklanmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve bir Işleyiciyi nasıl çağırır](how-the-framework-calls-a-handler.md)
