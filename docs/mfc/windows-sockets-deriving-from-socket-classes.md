---
title: 'Windows Yuvaları: Yuva sınıflarından türetme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- derived classes [MFC], from socket classes
- Windows Sockets [MFC], deriving from socket classes
- sockets [MFC], deriving from socket classes
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76ccb2ec126ae57e39b1a4fab3a0bff82a353d71
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953768"
---
# <a name="windows-sockets-deriving-from-socket-classes"></a>Windows Yuvaları: Yuva Sınıflarından Türetme
Bu makalede kendi sınıfı bir yuva sınıflarından türetme tarafından kazanmadan işlevselliği bazıları açıklanmaktadır.  
  
 Kendi yuva sınıflarından herhangi birinden türetilemeyeceğini [CAsyncSocket](../mfc/reference/casyncsocket-class.md) veya [CSocket](../mfc/reference/csocket-class.md) kendi işlevselliği eklemek için. Özellikle, bu sınıfları, kılabilirsiniz sanal üye işlevleri sağlar. Bu işlevler [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive), [OnSend](../mfc/reference/casyncsocket-class.md#onsend), [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept), [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect), ve [OnClose](../mfc/reference/casyncsocket-class.md#onclose). Ağ olaylar meydana geldiğinde sağladıkları bildirimleri yararlanmak için türetilen yuva sınıfınızda işlevleri geçersiz kılabilirsiniz. Çerçeve, veri alınmasını gibi önemli yuva olayların okuma başlayabilirsiniz bildirmek için bu bildirimi geri arama işlevleri çağırır. Bildirim işlevleri hakkında daha fazla bilgi için bkz: [Windows Yuvaları: Yuva bildirimleri](../mfc/windows-sockets-socket-notifications.md).  
  
 Ayrıca, sınıf `CSocket` sağlayan [OnMessagePending](../mfc/reference/csocket-class.md#onmessagepending) üye işlevi (Gelişmiş geçersiz kılınabilir). Yuva Windows tabanlı iletileri Pompalama sırada MFC bu işlevi çağırır. Geçersiz kılabilirsiniz `OnMessagePending` belirli iletileri Windows'dan aramak ve bunlara yanıt vermek için.  
  
 Varsayılan sürümü `OnMessagePending` sınıfında sağlanan `CSocket` bir engelleme çağrı tamamlanması beklenirken WM_PAINT iletileri için ileti sırası inceler. Görüntü kalitesini artırmak için boyama iletileri gönderir. Yararlı bir şeyi yapmanın yanı sıra, bu işlevi geçersiz kılabilir bir yolu kendiniz gösterilmektedir. Başka bir örnek olarak kullanmayı `OnMessagePending` aşağıdaki görev için. Bir ağ işlemi tamamlamak beklenirken bir kalıcı olmayan iletişim kutusu görüntüler varsayalım. İletişim kutusu kullanıcının uzun sürmesine engelleme işlemleri iptal etmek için kullanabileceği bir iptal düğmesi içerir. `OnMessagePending` Geçersiz kılma için bu kalıcı olmayan iletişim kutusunu ilgili iletileri pompa.  
  
 İçinde `OnMessagePending` geçersiz kılma, ya da dönüş **TRUE** veya return temel sınıf sürümü çağrısından `OnMessagePending`. Hala istediğiniz işlerini gerçekleştirirse temel sınıf sürüm çağırın.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Yuvaları: Engelleme](../mfc/windows-sockets-blocking.md)  
  
-   [Windows Yuvaları: Bayt Sıralama](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows Yuvaları: Dizeleri Dönüştürme](../mfc/windows-sockets-converting-strings.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)

