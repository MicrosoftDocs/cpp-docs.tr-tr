---
title: 'Windows Yuvaları: İşlem dizisi'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], operations
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- sockets [MFC], operations
- stream sockets [MFC]
ms.assetid: 43ce76f5-aad3-4247-b8a6-16cc7d012796
ms.openlocfilehash: 0f9fd339fdbdfee9381ea693568f40473c2397e9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265554"
---
# <a name="windows-sockets-sequence-of-operations"></a>Windows Yuvaları: İşlem dizisi

Bu makalede, yan yana sunucu yuvası ve istemci yuvası için işlemlerin sırasını gösterir. Yuva kullandığından `CArchive` nesneler oldukları mutlaka [akış yuvaları](../mfc/windows-sockets-stream-sockets.md).

## <a name="sequence-of-operations-for-a-stream-socket-communication"></a>Stream yuva iletişimi için işlem dizisi

Oluşturma noktaya kadar bir `CSocketFile` nesnesi (birkaç parametre farklılıklar) aşağıdaki sıra doğruysa hem `CAsyncSocket` ve `CSocket`. Bu noktadan itibaren içindir kesin olarak sıralı `CSocket`. Aşağıdaki tabloda, bir istemci ve sunucu arasında iletişim kurma için işlem dizisi gösterilmektedir.

### <a name="setting-up-communication-between-a-server-and-a-client"></a>Bir sunucu ve istemci arasında iletişim kurma

|Sunucu|İstemci|
|------------|------------|
|`// construct a socket`<br /><br /> `CSocket sockSrvr;`|`// construct a socket`<br /><br /> `CSocket sockClient;`|
|`// create the SOCKET`<br /><br /> `sockSrvr.Create(nPort);`1,2|`// create the SOCKET`<br /><br /> `sockClient.Create( );`2|
|`// start listening`<br /><br /> `sockSrvr.Listen( );`||
||`// seek a connection`<br /><br /> `sockClient.Connect(strAddr, nPort);`3,4|
|`// construct a new, empty socket`<br /><br /> `CSocket sockRecv;`<br /><br /> `// accept connection`<br /><br /> `sockSrvr.Accept( sockRecv );` 5||
|`// construct file object`<br /><br /> `CSocketFile file(&sockRecv);`|`// construct file object`<br /><br /> `CSocketFile file(&sockClient);`|
|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> -veya-<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> - veya her ikisi de-|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> -veya-<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> - veya her ikisi de-|
|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> -veya-<br /><br /> `arOut << dwValue;`6|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> -veya-<br /><br /> `arOut << dwValue;`6|

1. Burada *nbağlantı noktası* bir bağlantı noktası numarasıdır. Bkz: [Windows Yuvaları: Bağlantı noktaları ve yuva adresleri](../mfc/windows-sockets-ports-and-socket-addresses.md) bağlantı noktaları hakkında ayrıntılı bilgi için.

2. İstemciler bağlanabilmesi için sunucu her zaman bir bağlantı noktası belirtmeniz gerekir. `Create` Çağrı, bazen de bir adresi belirtir. İstemci tarafında, tüm kullanılabilir bağlantı noktası kullanmayı MFC isteyin varsayılan parametreleri kullanın.

3. Burada *nbağlantı noktası* bir bağlantı noktası numarası ve *strAddr* makine adresi veya bir Internet Protokolü (IP) adresi.

4. Makine adresleri birden fazla form alabilir: "ftp.microsoft.com", "microsoft.com". IP adresleri "noktalı sayı" form "127.54.67.32" kullanın. `Connect` (Bu sayı ağdaki geçerli bir makine olduğundan emin olmak için kontrol etmez rağmen) adresi noktalı bir sayı olup olmadığını görmek için işlev denetler. Aksi halde `Connect` diğer biçimlerden makine adını kabul eder.

5. Çağırdığınızda `Accept` sunucu tarafında geçirdiğiniz yeni bir yuva nesnesine bir başvuru. Bu nesne ilk oluşturmalıdır, ancak çağırmayın `Create` de. Aklınızda bu yuva nesnesi kapsamını, bağlantıyı kapatır aşması durumunda. MFC bağlanır yeni nesneye bir **YUVA** tanıtıcı. Yuva gösterildiği gibi yığını veya yığın oluşturabilirsiniz.

6. Bunlar kapsam dışına çıkmadan, arşiv ve yuva dosya kapatılır. Yuva nesnenin yok Edicisi de çağırır [Kapat](../mfc/reference/casyncsocket-class.md#close) nesne kapsam dışına gider veya silinirse yuva nesnesi için üye işlevi.

## <a name="additional-notes-about-the-sequence"></a>Sırası hakkında ek notlar

Yukarıdaki tabloda gösterilen çağrıları için bir akış yuva dizisidir. Bağlantısız olan veri birimi yuvaları gerektirmez [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect), [dinleme](../mfc/reference/casyncsocket-class.md#listen), ve [kabul](../mfc/reference/casyncsocket-class.md#accept) çağrıları (isteğe bağlı olarak kullanabilirsiniz,ancak`Connect`). Bunun yerine, sınıf kullanıyorsanız `CAsyncSocket`, veri birimi yuvaları kullanın `CAsyncSocket::SendTo` ve `ReceiveFrom` üye işlevleri. (Kullanırsanız `Connect` kullandığınız bir veri birimi yuvasıyla `Send` ve `Receive`.) Çünkü `CArchive` çalışmıyor veri birimi ile kullanmayın `CSocket` ile yuva bir veri birimi ise bir arşiv.

[CSocketFile](../mfc/reference/csocketfile-class.md) tüm desteklemiyor `CFile`'s işlevselliği; `CFile` üyeler gibi `Seek`, hangi hiçbir mantıklı bir yuva iletişimi için kullanılamaz. Bu nedenle, bazı varsayılan MFC `Serialize` işlevler ile uyumlu değildir `CSocketFile`. Bu, özellikle true `CEditView` sınıfı. Seri hale getirmek denememelisiniz `CEditView` verilerine bir `CArchive` nesne iliştirilmiş bir `CSocketFile` kullanarak nesne `CEditView::SerializeRaw`; kullanma `CEditView::Serialize` yerine (belgelenmemiştir). [SerializeRaw](../mfc/reference/ceditview-class.md#serializeraw) işlevi gibi işlevleri sağlamak için dosya nesnesi bekliyor `Seek`, o `CSocketFile` desteklemez.

Daha fazla bilgi için bkz.:

- [Windows Yuvaları: Yuvaları Arşivlerle kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: Sınıf Casyncsocket'ini kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Bağlantı noktaları ve yuva adresleri](../mfc/windows-sockets-ports-and-socket-addresses.md)

- [Windows Yuvaları: Stream yuva](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: Veri birimi yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[CSocket Sınıfı](../mfc/reference/csocket-class.md)<br/>
[CAsyncSocket::Create](../mfc/reference/casyncsocket-class.md#create)<br/>
[CAsyncSocket::Close](../mfc/reference/casyncsocket-class.md#close)
