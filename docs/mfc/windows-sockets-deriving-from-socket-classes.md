---
title: "Windows Yuvaları: Yuva sınıflarından türetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- derived classes [MFC], from socket classes
- Windows Sockets [MFC], deriving from socket classes
- sockets [MFC], deriving from socket classes
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0152afbafe7c4756bebd87f931b9a6b6f4e31269
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="windows-sockets-deriving-from-socket-classes"></a>Windows Yuvaları: Yuva Sınıflarından Türetme
Bu makalede kendi sınıfı bir yuva sınıflarından türetme tarafından kazanmadan işlevselliği bazıları açıklanmaktadır.  
  
 Kendi yuva sınıflarından herhangi birinden türetilemeyeceğini [CAsyncSocket](../mfc/reference/casyncsocket-class.md) veya [CSocket](../mfc/reference/csocket-class.md) kendi işlevselliği eklemek için. Özellikle, bu sınıfları, kılabilirsiniz sanal üye işlevleri sağlar. Bu işlevler [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive), [OnSend](../mfc/reference/casyncsocket-class.md#onsend), [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept), [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect), ve [OnClose](../mfc/reference/casyncsocket-class.md#onclose). Ağ olaylar meydana geldiğinde sağladıkları bildirimleri yararlanmak için türetilen yuva sınıfınızda işlevleri geçersiz kılabilirsiniz. Çerçeve, veri alınmasını gibi önemli yuva olayların okuma başlayabilirsiniz bildirmek için bu bildirimi geri arama işlevleri çağırır. Bildirim işlevleri hakkında daha fazla bilgi için bkz: [Windows Yuvaları: Yuva bildirimleri](../mfc/windows-sockets-socket-notifications.md).  
  
 Ayrıca, sınıf `CSocket` sağlayan [OnMessagePending](../mfc/reference/csocket-class.md#onmessagepending) üye işlevi (Gelişmiş geçersiz kılınabilir). Yuva Windows tabanlı iletileri Pompalama sırada MFC bu işlevi çağırır. Geçersiz kılabilirsiniz `OnMessagePending` belirli iletileri Windows'dan aramak ve bunlara yanıt vermek için.  
  
 Varsayılan sürümü `OnMessagePending` sınıfında sağlanan `CSocket` ileti sırası için inceler `WM_PAINT` bir engelleme çağrı tamamlanması beklenirken iletileri. Görüntü kalitesini artırmak için boyama iletileri gönderir. Yararlı bir şeyi yapmanın yanı sıra, bu işlevi geçersiz kılabilir bir yolu kendiniz gösterilmektedir. Başka bir örnek olarak kullanmayı `OnMessagePending` aşağıdaki görev için. Bir ağ işlemi tamamlamak beklenirken bir kalıcı olmayan iletişim kutusu görüntüler varsayalım. İletişim kutusu kullanıcının uzun sürmesine engelleme işlemleri iptal etmek için kullanabileceği bir iptal düğmesi içerir. `OnMessagePending` Geçersiz kılma için bu kalıcı olmayan iletişim kutusunu ilgili iletileri pompa.  
  
 İçinde `OnMessagePending` geçersiz kılma, ya da dönüş **TRUE** veya return temel sınıf sürümü çağrısından `OnMessagePending`. Hala istediğiniz işlerini gerçekleştirirse temel sınıf sürüm çağırın.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Windows Yuvaları: Yuvaları Arşivlerle kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Yuvaları: Sınıf Casyncsocket'ini kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Yuvaları: engelleme](../mfc/windows-sockets-blocking.md)  
  
-   [Windows Yuvaları: Bayt sıralama](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows Yuvaları: Dizeleri dönüştürme](../mfc/windows-sockets-converting-strings.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)

