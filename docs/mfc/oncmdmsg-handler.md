---
description: 'Daha fazla bilgi edinin: OnCmdMsg Işleyicisi'
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
ms.openlocfilehash: 69dfbd7ccc52a6d90b57ef9cedf0f896d65057b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243971"
---
# <a name="oncmdmsg-handler"></a>OnCmdMsg İşleyicisi

Komutların yönlendirilmesini başarmak için, her komut hedefi `OnCmdMsg` dizideki bir sonraki komut hedefinin üye işlevini çağırır. Komut hedefleri, `OnCmdMsg` bir komutu işleyebilecekleri ve işleyememesi durumunda onu başka bir komut hedefine yönlendirip işleyemeyeceğini belirlemede kullanır.

Her komut hedefi sınıfı üye işlevini geçersiz kılabilir `OnCmdMsg` . Geçersiz kılmalar her bir sınıfın komut için belirli bir sonraki hedefe yol almasına izin verir. Örneğin, bir çerçeve penceresi, her zaman komutları geçerli alt penceresine veya görünümüne, tablo [standart komut rotasında](command-routing.md)gösterildiği gibi yönlendirir.

Varsayılan `CCmdTarget` uygulama, `OnCmdMsg` aldığı her komut iletisi için bir işleyici işlevi aramak üzere komut-hedef sınıfının ileti eşlemesini kullanır ve standart mesajların aranacağı şekilde. Bir eşleşme bulunursa işleyiciyi çağırır. İleti eşleme araması [, Framework 'Ün Ileti eşlemelerini arayacağı](how-the-framework-searches-message-maps.md)şekilde açıklanmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve bir Işleyiciyi nasıl çağırır](how-the-framework-calls-a-handler.md)
