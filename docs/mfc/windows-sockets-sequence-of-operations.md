---
description: 'Daha fazla bilgi edinin: Windows Yuvaları: Işlem dizisi'
title: 'Windows Yuvaları: İşlem Dizisi'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], operations
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- sockets [MFC], operations
- stream sockets [MFC]
ms.assetid: 43ce76f5-aad3-4247-b8a6-16cc7d012796
ms.openlocfilehash: 89870de642abcc8e0584c2c5dc93860eda9785e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263380"
---
# <a name="windows-sockets-sequence-of-operations"></a>Windows Yuvaları: İşlem Dizisi

Bu makalede, bir sunucu yuvası ve bir istemci yuvası için işlem sırası ve yan yana gösterilmektedir. Yuvalar `CArchive` nesneleri kullandığından, [akış yuvaları](../mfc/windows-sockets-stream-sockets.md)olması gerekir.

## <a name="sequence-of-operations-for-a-stream-socket-communication"></a>Akış yuvası Iletişimi için Işlem dizisi

Bir nesne oluşturma noktasına kadar `CSocketFile` , hem hem de için aşağıdaki sıra doğru (birkaç parametre farimiyle) `CAsyncSocket` `CSocket` . Bu noktadan itibaren, sırası kesinlikle içindir `CSocket` . Aşağıdaki tabloda, bir istemci ile sunucu arasındaki iletişimi ayarlamaya yönelik işlemlerin sırası gösterilmektedir.

### <a name="setting-up-communication-between-a-server-and-a-client"></a>Sunucu ile Istemci arasında Iletişim kurma

|Sunucu|İstemci|
|------------|------------|
|`// construct a socket`<br /><br /> `CSocket sockSrvr;`|`// construct a socket`<br /><br /> `CSocket sockClient;`|
|`// create the SOCKET`<br /><br /> `sockSrvr.Create(nPort);`1, 2|`// create the SOCKET`<br /><br /> `sockClient.Create( );`iki|
|`// start listening`<br /><br /> `sockSrvr.Listen( );`||
||`// seek a connection`<br /><br /> `sockClient.Connect(strAddr, nPort);`3, 4|
|`// construct a new, empty socket`<br /><br /> `CSocket sockRecv;`<br /><br /> `// accept connection`<br /><br /> `sockSrvr.Accept( sockRecv );` e||
|`// construct file object`<br /><br /> `CSocketFile file(&sockRecv);`|`// construct file object`<br /><br /> `CSocketFile file(&sockClient);`|
|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> -veya-<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> -veya her Ikisi-|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> -veya-<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> -veya her Ikisi-|
|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> -veya-<br /><br /> `arOut << dwValue;`inç|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> -veya-<br /><br /> `arOut << dwValue;`inç|

1. Burada *nport* bir bağlantı noktası numarasıdır. Bağlantı noktaları hakkında ayrıntılı bilgi için bkz. [Windows Yuvaları: bağlantı noktaları ve yuva adresleri](../mfc/windows-sockets-ports-and-socket-addresses.md) .

2. İstemcilerin bağlanabilmesi için sunucunun her zaman bir bağlantı noktası belirtmesi gerekir. `Create`Çağrı bazen bir adresi de belirtir. İstemci tarafında, MFC 'nin kullanılabilir herhangi bir bağlantı noktasını kullanmasını istemek için varsayılan parametreleri kullanın.

3. Burada *Nport* bir bağlantı noktası numarasıdır ve *straddr* bir makine adresi veya Internet Protokolü (IP) adresidir.

4. Makine adresleri birkaç form alabilir: "ftp.microsoft.com", "microsoft.com". IP adresleri "127.54.67.32" "noktalı sayı" formunu kullanır. `Connect`İşlevi, adresin noktalı bir sayı olup olmadığını denetler (ancak numaranın ağdaki geçerli bir makine olduğundan emin olup olmadığını denetlemez). Aksi takdirde, `Connect` diğer formlardan birinin makine adını varsayar.

5. `Accept`Sunucu tarafında çağırdığınızda, yeni bir yuva nesnesine bir başvuru geçirirsiniz. Önce bu nesneyi oluşturmanız gerekir, ancak bunu çağırmayın `Create` . Bu yuva nesnesi kapsam dışına geçtiğinde bağlantının kapandığını aklınızda bulundurun. MFC yeni nesneyi bir **yuva** tanıtıcısına bağlar. Yuva üzerinde veya yığında veya yığında oluşturabilirsiniz.

6. Arşiv ve yuva dosyası, kapsam dışına gittiklerinde kapalıdır. Yuva nesnesinin yıkıcısı, nesne kapsam dışına geçtiğinde ya da silindiğinde yuva nesnesi için [Close](../mfc/reference/casyncsocket-class.md#close) üye işlevini çağırır.

## <a name="additional-notes-about-the-sequence"></a>Dizi hakkında ek notlar

Yukarıdaki tabloda gösterilen çağrıların sırası, Stream yuvası içindir. Bağlantısız olan veri birimi yuvaları, [CAsyncSocket:: Connect](../mfc/reference/casyncsocket-class.md#connect), [dinlemesi](../mfc/reference/casyncsocket-class.md#listen)ve [kabul etme](../mfc/reference/casyncsocket-class.md#accept) çağrılarına (isteğe bağlı olarak da kullanabilirsiniz) gerek yoktur `Connect` . Bunun yerine, sınıfı kullanıyorsanız `CAsyncSocket` , veri birimi yuvaları `CAsyncSocket::SendTo` ve `ReceiveFrom` üye işlevlerini kullanır. ( `Connect` Bir veri birimi yuvası ile kullanıyorsanız, `Send` ve kullanırsınız `Receive` .) `CArchive` , İş birimleri ile çalışmadığından, `CSocket` yuva bir veri birimi ise, bir arşiv ile kullanmayın.

[CSocketFile](../mfc/reference/csocketfile-class.md) `CFile` , tüm işlevleri desteklemez; gibi `CFile` `Seek` bir yuva iletişimi için bir fikir sahibi olmayan Üyeler kullanılamaz. Bu nedenle, bazı varsayılan MFC `Serialize` işlevleri ile uyumlu değildir `CSocketFile` . Bu, sınıfının özellikle de doğrudur `CEditView` . `CEditView`Kullanarak bir nesneye eklenen bir nesne aracılığıyla veri serileştirmenize çalışmayın `CArchive` `CSocketFile` `CEditView::SerializeRaw` ; `CEditView::Serialize` bunun yerine kullanın (belgelenmemiş). [Serializsilinebilir w](../mfc/reference/ceditview-class.md#serializeraw) işlevi dosya nesnesinin, gibi işlevleri olmasını bekler `Seek` `CSocketFile` .

Daha fazla bilgi için bkz:

- [Windows Yuvaları: Arşivlerle yuvaları kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: sınıf CAsyncSocket kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: bağlantı noktaları ve yuva adresleri](../mfc/windows-sockets-ports-and-socket-addresses.md)

- [Windows Yuvaları: akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: veri birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[CSocket sınıfı](../mfc/reference/csocket-class.md)<br/>
[CAsyncSocket:: Create](../mfc/reference/casyncsocket-class.md#create)<br/>
[CAsyncSocket:: Close](../mfc/reference/casyncsocket-class.md#close)
