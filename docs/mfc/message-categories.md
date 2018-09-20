---
title: İleti kategorileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], categories
- control-notification messages [MFC]
- Windows messages [MFC], categories
- controls [MFC], notifications
- command messages [MFC]
- messages [MFC], Windows
- message handling [MFC], message types
ms.assetid: 68e1db75-9da6-4a4d-b2c2-dc4d59f8d87b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b1b8da6f6c1b94432d9cd4c91d88f6d844fbb27
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433055"
---
# <a name="message-categories"></a>İleti Kategorileri

Üç ana kategori için ne tür bir ileti işleyicileri yazma:

1. Windows iletileri

     Bu, öncelikle başlayarak iletileri içerir **WM_** WM_COMMAND dışında bir önek. Windows iletileri, windows ve görünümler tarafından işlenir. Bu iletiler genellikle iletisini işlemek nasıl belirlemek için kullanılan parametrelere sahiptir.

1. Denetim bildirimleri

     Bu, kendi üst windows denetimleri ve diğer alt pencereleri WM_COMMAND bildirim iletileri içerir. Örneğin, bir düzenleme denetiminin üst kullanıcının düzenleme denetiminde metni değiştirmiş bir eylem durumdayken EN_CHANGE denetim bildirimi kodu içeren bir WM_COMMAND ileti gönderir. İleti için Pencere işleyicisi bildirim iletisi denetimdeki metin alma gibi uygun bir şekilde yanıt verir.

     Çerçeve denetim bildirimi iletileri gibi diğer yolları **WM_** iletileri. Bir özel durum, ancak kullanıcı bunları tıkladığında düğmeler tarafından gönderilen BN_CLICKED denetim bildirimi ileti olabilir. Bu iletiyi özel bir komut iletisi olarak kabul edilir ve gibi başka komutlar yönlendirilir.

1. Komut iletileri

     Bu kullanıcı arabirimi nesneleri içinden WM_COMMAND bildirim iletileri içerir: menüleri ve araç çubuğu düğmeleri kısayol tuşları. Diğer iletiler komutlarından farklı framework işler ve bunlar daha fazla türde nesneler tarafından açıklandığı şekilde işlenebilir [komut hedefleri](../mfc/command-targets.md).

##  <a name="_core_windows_messages_and_control.2d.notification_messages"></a> Windows iletilerini ve denetim bildirimi iletileri

İletileri kategorilerdeki 1 ve 2 — Windows iletileri ve denetim bildirimleri — windows tarafından işlenir: sınıfından türetilmiş sınıfların nesneleri `CWnd`. Bu içerir `CFrameWnd`, `CMDIFrameWnd`, `CMDIChildWnd`, `CView`, `CDialog`, ve bu temel sınıfların kendi sınıflar türetilmiş. Bu tür nesneler kapsülleyen bir `HWND`, bir Windows penceresi için bir tanıtıcı.

##  <a name="_core_command_messages"></a> Komut iletileri

İletileri kategorisinde 3 — komutları — çeşitli nesneleri tarafından işlenebilir: belgeleri ve belge şablonları uygulama nesnesinin kendisi yanı sıra windows ve görünümler. Bir komut bazı belirli nesne doğrudan etkilediğinde, söz konusu nesne komutunu işlemek için mantıklıdır. Örneğin, Dosya menüsündeki Aç komutunu uygulamayla mantıksal olarak ilişkili: komut alındıktan sonra belirtilen bir belge uygulama açılır. Bu nedenle açık komut işleyicisi uygulama sınıfının bir üye işlevidir. Komutlar ve nesnelere nasıl yönlendirileceğini hakkında daha fazla bilgi için bkz. [Framework'ün işleyici çağırması](../mfc/how-the-framework-calls-a-handler.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)

