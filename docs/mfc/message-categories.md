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
ms.openlocfilehash: 051fe93ef689959b0a0beb2b1b0f213adc942446
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929653"
---
# <a name="message-categories"></a>İleti Kategorileri
Üç ana kategoride için ne tür iletileri işleyicileri yazma:  
  
1.  Windows iletileri  
  
     Bu, öncelikle itibaren iletileri içerir **WM_** WM_COMMAND dışında öneki. Windows iletileri, windows ve görünümler tarafından işlenir. Bu iletiler genellikle iletinin ne yapılacağını belirlemek için kullanılan parametreleri sahiptir.  
  
2.  Denetim bildirimleri  
  
     Bu, kendi üst Windows denetimleri ve diğer alt windows WM_COMMAND bildirim iletilerini içerir. Örneğin, bir düzenleme denetimine üst kullanıcı metin düzenleme denetimindeki değiştirmiş bir eylem durumdayken EN_CHANGE denetim bildirimi kodu içeren bir WM_COMMAND ileti gönderir. İleti için pencerenin işleyicisi bildirim iletisi denetiminde metin alma gibi bazı uygun şekilde yanıt verir.  
  
     Denetim bildirimi iletileri gibi diğer framework yönlendiren **WM_** iletileri. Bir özel durum, ancak kullanıcı bunları tıklattığında düğmelerin tarafından gönderilen BN_CLICKED denetim bildirimi iletisidir. Bu ileti özel bir komut iletisi olarak kabul edilir ve gibi başka komutlar yönlendirilir.  
  
3.  Komut iletileri  
  
     Bu kullanıcı arabirimi nesneleri WM_COMMAND bildirim iletilerini içerir: menüleri ve araç çubuğu düğmeleri Hızlandırıcı tuşları. Diğer iletileri farklı komutlarından framework işler ve bunlar daha fazla tür nesneler tarafından açıklandığı şekilde işlenebilir [komut hedefleri](../mfc/command-targets.md).  
  
##  <a name="_core_windows_messages_and_control.2d.notification_messages"></a> Windows iletileri ve denetim bildirimi iletileri  
 1 ve 2 kategorilerdeki iletileri — Windows iletileri ve denetim bildirimleri — windows tarafından işlenen: sınıfların nesnelerini sınıfından türetilen `CWnd`. Bu içerir `CFrameWnd`, `CMDIFrameWnd`, `CMDIChildWnd`, `CView`, `CDialog`, ve kendi sınıflarınızı bu temel sınıflardan türetilmiş. Bu tür nesneleri kapsülleyen bir `HWND`, bir Windows penceresi için bir tanıtıcı.  
  
##  <a name="_core_command_messages"></a> Komut iletileri  
 İletileri kategorisinde 3 — komutları — çeşitli nesneleri tarafından işlenebilir: belgeleri, belge şablonları ve uygulama nesnesi kendisini yanı sıra windows ve görünümler. Bir komut doğrudan bazı belirli nesne etkilediğinde, söz konusu nesne komutu işlemek için mantıklıdır. Örneğin, Dosya menüsündeki Aç komutu uygulamayla mantıksal olarak ilişkilendirilen: uygulama komut alındıktan sonra belirtilen bir belge açılır. Bu nedenle Aç komutu için uygulama sınıfının üye işlevi işleyicidir. Komutlar ve nesnelere nasıl yönlendirildiği hakkında daha fazla bilgi için bkz: [Framework bir işleyici çağırması](../mfc/how-the-framework-calls-a-handler.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)

