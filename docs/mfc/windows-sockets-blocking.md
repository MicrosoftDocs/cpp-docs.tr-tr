---
title: "Windows Yuvaları: Engelleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- sockets [MFC], blocking mode
- Windows Sockets [MFC], Windows platforms
- Windows Sockets [MFC], blocking mode
- sockets [MFC], behavior on different Windows platforms
- blocking mode sockets
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b4b54b78034037e9f3b015d7c1f67bb33771248c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-blocking"></a>Windows Yuvaları: Engelleme
Bu makale ve iki yardımcı makaleler Windows Sockets programlamada çeşitli sorunlar açıklanmaktadır. Bu makalede, engelleme yer almaktadır. Diğer sorunlar makalelerinde ele alınmıştır: [Windows Yuvaları: bayt sıralama](../mfc/windows-sockets-byte-ordering.md) ve [Windows Yuvaları: dizeleri dönüştürme](../mfc/windows-sockets-converting-strings.md).  
  
 Kullanıyorsanız veya sınıfından türetilen [CAsyncSocket](../mfc/reference/casyncsocket-class.md), bu sorunları kendiniz yönetmeniz gerekir. Kullanıyorsanız veya sınıfından türetilen [CSocket](../mfc/reference/csocket-class.md), MFC yönetir bunları sizin için.  
  
## <a name="blocking"></a>Engelleme  
 Bir yuva "engelleme modu" veya "sayıda modu." olabilir Kendi eylem tamamlanmasını engelleyen (veya zaman uyumlu) modunda yuva işlevleri döndürmeyin. Bu, işlevi çağrıldı yuva hiçbir şey yapamaz çünkü engelleme adlandırılır — engellendi — çağrı dönene kadar. Çağrı **alma** üye işlevi, örneğin, gönderen uygulama göndermek bekleyeceği gibi tamamlamak için bir rasgele uzun sürebilir (kullanıyorsanız budur `CSocket`, veya kullanarak `CAsyncSocket` engelleme ile). Varsa bir `CAsyncSocket` nesne çağrı döndürür hemen (zaman uyumsuz olarak işletim) sayıda modunda olduğundan ve geçerli hata kodu ile alınabilir [GetLastError](../mfc/reference/casyncsocket-class.md#getlasterror) üye işlevidir **WSAEWOULDBLOCK**, çağrı engelleyecek olduğunu belirten, vardı, hemen nedeniyle modu döndürülmedi. (`CSocket` hiçbir zaman döndürür **WSAEWOULDBLOCK**. Sınıfı sizin için engelleme yönetir.)  
  
 Yuva davranışını 32-bit ve 64-bit işletim sistemleri (örneğin, Windows 95 veya Windows 98) 16-bit işletim sistemleri (örneğin, Windows 3.1) altında altında farklıdır. 16 bit işletim sistemleri, aksine 32-bit ve 64-bit işletim sistemlerinde PreEmptive tarafından görevli kullanın ve çoklu iş parçacığı kullanımı sağlayın. 32 bit ve 64-bit işletim sistemlerinde ayrı çalışan iş parçacıkları, yuva koyabilirsiniz. Bir iş parçacığı yuvası engellemesine işlem süresi harcama olmadan ve uygulamanızdaki diğer etkinlikler müdahale engelleyebilirsiniz. Birden çok iş parçacıklı programlama hakkında daha fazla bilgi için bkz: [çoklu iş parçacığı kullanımı](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
> [!NOTE]
>  Birden çok iş parçacıklı uygulamalarda engelleme yapısını kullanabilirsiniz `CSocket` kullanıcı arabiriminin yanıtlama etkilemeden programınızın tasarım basitleştirmek için. Kullanıcı etkileşimleri ana iş parçacığında işleme tarafından ve `CSocket` alternatif iş parçacıklarında işleme, bu mantıksal işlemleri ayırabilirsiniz. Birden çok iş parçacıklı olmayan bir uygulamada, bu iki etkinlik birleştirilmiş ve gerekir anlamı genellikle kullanarak tek bir iş ele `CAsyncSocket` isteğe bağlı veya geçersiz kılma iletişimleri istekleri işleyebilmesi için `CSocket::OnMessagePending` kullanıcı eylemlerini işlemek için uzun zaman uyumlu etkinliği.  
  
 Bu tartışma kalan 16-bit işletim sistemlerini hedefleme programcıları içindir:  
  
 Normalde, kullanıyorsanız `CAsyncSocket`, engelleme işlemleri kullanmaktan kaçının ve bunun yerine zaman uyumsuz olarak çalışır. Hangi aldığınız noktasından zaman uyumsuz işlemleri bir **WSAEWOULDBLOCK** çağırdıktan sonra hata kodu **alma**, örneğin, kadar bekleyin, `OnReceive` üye çağrıldığında bildirmek için size yeniden okuyabilir. Zaman uyumsuz çağrılar geri yuva 's uygun geri bildirim işlevi gibi çağırarak yapılma [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive).  
  
 Windows altında engelleme çağrıları hatalı yöntem olarak kabul edilir. Varsayılan olarak, [CAsyncSocket](../mfc/reference/casyncsocket-class.md) destekleyen zaman uyumsuz çağrılar ve yönetmelidir geri bildirimleri kullanarak kendiniz engelleme. Sınıf [CSocket](../mfc/reference/csocket-class.md), diğer yandan, zaman uyumlu değil. Windows iletileri Pompalar ve sizin için engelleme yönetir.  
  
 Windows Yuvaları belirtimi engelleme hakkında daha fazla bilgi için bkz. Hakkında daha fazla bilgi için "" işlevleri, bkz: [Windows Yuvaları: Yuva bildirimleri](../mfc/windows-sockets-socket-notifications.md) ve [Windows Yuvaları: Yuva sınıflarından türetme](../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
 Daha fazla bilgi için bkz.:  
  
-   [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)  
  
-   [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)   
 [CAsyncSocket::OnSend](../mfc/reference/casyncsocket-class.md#onsend)

