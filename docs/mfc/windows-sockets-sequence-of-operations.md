---
title: 'Windows Yuvaları: İşlem dizisi | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], operations
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- sockets [MFC], operations
- stream sockets [MFC]
ms.assetid: 43ce76f5-aad3-4247-b8a6-16cc7d012796
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c27856b2bb6b843ce60404ea389c28082bf1dc5a
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953951"
---
# <a name="windows-sockets-sequence-of-operations"></a>Windows Yuvaları: İşlem Dizisi
Bu makalede yan yana server yuva ve bir istemci yuva için işlem dizisi gösterilmektedir. Yuva kullandığından `CArchive` nesneleri, mutlaka oldukları [akış yuvaları](../mfc/windows-sockets-stream-sockets.md).  
  
## <a name="sequence-of-operations-for-a-stream-socket-communication"></a>Bir akışa yuva iletişimi için işlem dizisi  
 Oluşturma, noktaya kadar bir `CSocketFile` nesne (birkaç parametre farklılıklar) aşağıdaki sıra doğruysa her ikisi için de `CAsyncSocket` ve `CSocket`. Bu noktadan itibaren içindir kesinlikle dizisi `CSocket`. Aşağıdaki tabloda, bir istemci ve sunucu arasında iletişim kurma için işlem dizisi gösterilmektedir.  
  
### <a name="setting-up-communication-between-a-server-and-a-client"></a>Bir sunucu ve istemci arasında iletişim kurma  
  
|Sunucu|İstemci|  
|------------|------------|  
|`// construct a socket`<br /><br /> `CSocket sockSrvr;`|`// construct a socket`<br /><br /> `CSocket sockClient;`|  
|`// create the SOCKET`<br /><br /> `sockSrvr.Create(nPort);`1,2|`// create the SOCKET`<br /><br /> `sockClient.Create( );`2|  
|`// start listening`<br /><br /> `sockSrvr.Listen( );`||  
||`// seek a connection`<br /><br /> `sockClient.Connect(strAddr, nPort);`3,4|  
|`// construct a new, empty socket`<br /><br /> `CSocket sockRecv;`<br /><br /> `// accept connection`<br /><br /> `sockSrvr.Accept( sockRecv );` 5||  
|`// construct file object`<br /><br /> `CSocketFile file(&sockRecv);`|`// construct file object`<br /><br /> `CSocketFile file(&sockClient);`|  
|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> veya<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> - veya her ikisi de-|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> veya<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> - veya her ikisi de-|  
|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> veya<br /><br /> `arOut << dwValue;`6|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> veya<br /><br /> `arOut << dwValue;`6|  
  
 1. Burada *nbağlantı noktası* bir bağlantı noktası numarasıdır. Bkz: [Windows Yuvaları: bağlantı noktaları ve yuva adresleri](../mfc/windows-sockets-ports-and-socket-addresses.md) bağlantı noktaları hakkında ayrıntılı bilgi için.  
  
 2. İstemcileri bağlanabilmesi için sunucu her zaman bir bağlantı noktası belirtmeniz gerekir. `Create` Çağrısı bazen de bir adresini belirtir. İstemci tarafında, tüm kullanılabilir bağlantı noktası kullanmak için MFC isteyin varsayılan parametreleri kullanın.  
  
 3. Burada *nbağlantı noktası* bir bağlantı noktası numarası ve *strAddr* makine adresi veya bir Internet Protokolü (IP) adresi.  
  
 4. Makine adresleri birden fazla form alabilir: "ftp.microsoft.com", "microsoft.com". IP adresleri "numarası noktalı" form "127.54.67.32" kullanın. `Connect` İşlevi (Bu sayı ağdaki geçerli bir makine olduğundan emin olmak için kontrol etmez rağmen) adresini noktalı bir sayı olup olmadığını denetler. Aksi durumda, `Connect` bir makine adını diğer biçimlerden birini varsayar.  
  
 5. Çağırdığınızda `Accept` sunucu tarafında yeni bir yuva nesnesi başvuru geçirin. Bu nesnenin ilk oluşturmalıdır, ancak çağırmayın `Create` onun için. Aklınızda bu yuva nesnesi kapsamını, bağlantıyı kapatır kalırsa. MFC yeni nesneye bağlanan bir **YUVA** işler. Yığında gösterildiği gibi ya da yığında yuva oluşturabilirsiniz.  
  
 6. Kapsam dışında olduğunuzda Arşiv ve yuva dosya kapatılır. Yuva nesnenin yıkıcı de çağırır [Kapat](../mfc/reference/casyncsocket-class.md#close) üye işlevi yuva nesnesinin nesne kapsam dışında gider ya da silinir.  
  
## <a name="additional-notes-about-the-sequence"></a>Sırası hakkında ek notlar  
 Önceki tabloda gösterilen çağrıları için bir akışa yuva dizisidir. Bağlantısız, veri birimi yuvaları gerektirmez [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect), [dinleme](../mfc/reference/casyncsocket-class.md#listen), ve [kabul](../mfc/reference/casyncsocket-class.md#accept) çağrıları (isteğe bağlı olarak kullanmanızmümkünolmaklabirlikte`Connect`). Bunun yerine, sınıf kullanıyorsanız `CAsyncSocket`, veri birimi yuvaları kullanım `CAsyncSocket::SendTo` ve `ReceiveFrom` üye işlevleri. (Kullanırsanız `Connect` bir veri birimi yuvası ile kullandığınız `Send` ve `Receive`.) Çünkü `CArchive` çalışmıyor veri birimi ile kullanmayın `CSocket` yuva bir veri birimi ise bir arşiv ile.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md) tüm desteklemiyor `CFile`'s işlevselliği; `CFile` üyeleri gibi `Seek`, hangi hiçbir anlamlı bir yuva iletişimi için kullanılamaz. Bu nedenle, bazı varsayılan MFC `Serialize` işlevleri ile uyumlu olmadığında `CSocketFile`. Bu özellikle, geçerlidir `CEditView` sınıfı. Değil seri denemelisiniz `CEditView` verilerine bir `CArchive` nesne iliştirilmiş bir `CSocketFile` kullanarak nesne `CEditView::SerializeRaw`; kullanın `CEditView::Serialize` yerine (belgelenmemiştir). [SerializeRaw](../mfc/reference/ceditview-class.md#serializeraw) işlev, İşlevler, sahip için dosya nesnesi bekliyor `Seek`, o `CSocketFile` desteklemiyor.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Yuvaları: Bağlantı Noktaları ve Yuva Adresleri](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
-   [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)   
 [CSocket sınıfı](../mfc/reference/csocket-class.md)   
 [CAsyncSocket::Create](../mfc/reference/casyncsocket-class.md#create)   
 [CAsyncSocket::Close](../mfc/reference/casyncsocket-class.md#close)

