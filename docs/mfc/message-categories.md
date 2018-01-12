---
title: "İleti kategorileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- messages [MFC], categories
- control-notification messages [MFC]
- Windows messages [MFC], categories
- controls [MFC], notifications
- command messages [MFC]
- messages [MFC], Windows
- message handling [MFC], message types
ms.assetid: 68e1db75-9da6-4a4d-b2c2-dc4d59f8d87b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: be3bc617c0f3a9915c7ae0314b0e3889ecc561f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="message-categories"></a>İleti Kategorileri
Üç ana kategoride için ne tür iletileri işleyicileri yazma:  
  
1.  Windows iletileri  
  
     Bu, öncelikle itibaren iletileri içerir **WM_** öneki dışında **WM_COMMAND**. Windows iletileri, windows ve görünümler tarafından işlenir. Bu iletiler genellikle iletinin ne yapılacağını belirlemek için kullanılan parametreleri sahiptir.  
  
2.  Denetim bildirimleri  
  
     Bu içerir **WM_COMMAND** denetimleri ve diğer alt windows kendi üst Windows bildirim iletileri. Örneğin, bir düzenleme denetimine üst gönderir bir **WM_COMMAND** iletisini içeren **EN_CHANGE** kullanıcı, bir eylem gerçekleştirdiği olduğunda denetim bildirimi kod, metin düzenleme denetimindeki değiştirilmiş. İleti için pencerenin işleyicisi bildirim iletisi denetiminde metin alma gibi bazı uygun şekilde yanıt verir.  
  
     Denetim bildirimi iletileri gibi diğer framework yönlendiren **WM_** iletileri. Ancak, bir özel durum olan **BN_CLICKED** kullanıcı bunları tıklattığında düğmelerin tarafından gönderilen denetim bildirim iletisi. Bu ileti özel bir komut iletisi olarak kabul edilir ve gibi başka komutlar yönlendirilir.  
  
3.  Komut iletileri  
  
     Bu içerir **WM_COMMAND** kullanıcı arabirimi nesneleri bildirim iletileri: menüleri ve araç çubuğu düğmeleri Hızlandırıcı tuşları. Diğer iletileri farklı komutlarından framework işler ve bunlar daha fazla tür nesneler tarafından açıklandığı şekilde işlenebilir [komut hedefleri](../mfc/command-targets.md).  
  
##  <a name="_core_windows_messages_and_control.2d.notification_messages"></a>Windows iletileri ve denetim bildirimi iletileri  
 1 ve 2 kategorilerdeki iletileri — Windows iletileri ve denetim bildirimleri — windows tarafından işlenen: sınıfların nesnelerini sınıfından türetilen `CWnd`. Bu içerir `CFrameWnd`, `CMDIFrameWnd`, `CMDIChildWnd`, `CView`, `CDialog`, ve kendi sınıflarınızı bu temel sınıflardan türetilmiş. Bu tür nesneleri kapsülleyen bir `HWND`, bir Windows penceresi için bir tanıtıcı.  
  
##  <a name="_core_command_messages"></a>Komut iletileri  
 İletileri kategorisinde 3 — komutları — çeşitli nesneleri tarafından işlenebilir: belgeleri, belge şablonları ve uygulama nesnesi kendisini yanı sıra windows ve görünümler. Bir komut doğrudan bazı belirli nesne etkilediğinde, söz konusu nesne komutu işlemek için mantıklıdır. Örneğin, Dosya menüsündeki Aç komutu uygulamayla mantıksal olarak ilişkilendirilen: uygulama komut alındıktan sonra belirtilen bir belge açılır. Bu nedenle Aç komutu için uygulama sınıfının üye işlevi işleyicidir. Komutlar ve nesnelere nasıl yönlendirildiği hakkında daha fazla bilgi için bkz: [Framework bir işleyici çağırması](../mfc/how-the-framework-calls-a-handler.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)

