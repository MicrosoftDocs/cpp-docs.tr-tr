---
title: 'Windows Yuvaları: Bayt Sıralama'
ms.date: 11/04/2016
helpviewer_keywords:
- byte order issues in sockets programming
- sockets [MFC], byte order issues
- Windows Sockets [MFC], byte order issues
ms.assetid: 8a787a65-f9f4-4002-a02f-ac25a5dace5d
ms.openlocfilehash: 74d3b53ae3ab476ef1224caed91f31929fcce1ff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453958"
---
# <a name="windows-sockets-byte-ordering"></a>Windows Yuvaları: Bayt Sıralama

Bu makale ve iki Yardımcısı makaleler Windows Sockets programlamada çeşitli sorunlar açıklanmaktadır. Bu makale, bayt sıralama kapsar. Diğer sorunlar makalelerde ele alınmıştır: [Windows Yuvaları: engelleme](../mfc/windows-sockets-blocking.md) ve [Windows Yuvaları: dizeleri dönüştürme](../mfc/windows-sockets-converting-strings.md).

Kullanıyorsanız veya sınıfından türetilir [Casyncsocket'ini](../mfc/reference/casyncsocket-class.md), bu sorunları kendiniz yönetmeniz gerekecek. Kullanıyorsanız veya sınıfından türetilir [CSocket](../mfc/reference/csocket-class.md), MFC yönetir bunlar sizin için.

## <a name="byte-ordering"></a>Bayt sıralama

Farklı makine mimarileri bazen farklı bayt kullanarak verileri depolar. Örneğin, Intel tabanlı makineler Macintosh (Motorola) makineleri ters sırada verileri depolar. "Endian," adlı Intel bayt sırası Ayrıca ağ standart "big-Endian" sıranın tersidir. Aşağıdaki tabloda bu terimlerin açıklanmaktadır.

### <a name="big--and-little-endian-byte-ordering"></a>Büyük ve küçük-Endian bayt sıralama

|Bayt sıralama|Açıklama|
|-------------------|-------------|
|Büyük Endian|En önemli bir sözcük sol tarafta bayttır.|
|Küçük Endian|En önemli bir sözcük sağ tarafta bayttır.|

Genellikle, ağ üzerinden gönderip veriler için bayt sırası dönüştürme hakkında endişelenmeniz gerekmez, ancak bazı durumlarda bayt dönüştürmeniz gerekir.

## <a name="when-you-must-convert-byte-orders"></a>Bayt dönüştürürken gerekir

Aşağıdaki durumlarda bayt siparişlerini dönüştürmek yapmanız gerekir:

- Başka bir makineye gönderdiğiniz veri aksine bir ağ olarak yorumlanması gereken bilgileri geçiriliyor. Örneğin, geçebilir bağlantı noktaları ve adresleri, ağ anlamanız gerekir.

- Sunucu uygulaması ile iletişim kuran bir MFC uygulaması değil (ve kaynak kodu için erişiminiz yok). İki makine aynı bayt sıralama paylaşmıyorsa bu bayt sırası dönüştürmeleri için çağırır.

## <a name="when-you-do-not-have-to-convert-byte-orders"></a>Ne zaman Dönüştür bayt gerekmez

Aşağıdaki durumlarda bayt siparişlerini dönüştürme işi önleyebilirsiniz:

- Her iki ucunda makineler bayt takas değil kabul edebilir ve her iki makine aynı bayt sırası kullanın.

- Sunucu ile iletişim kuran bir MFC uygulamasıdır.

- Bayt veya dönüştürmeniz gerekir olup olmadığını açıkça söyleyebilirsiniz şekilde sunucusu ile iletişim için kaynak kodu sahip.

- MFC sunucuya bağlantı noktası. Bunu yapmak oldukça kolaydır ve genellikle daha küçük, daha hızlı kod sonucudur.

Çalışma [Casyncsocket'ini](../mfc/reference/casyncsocket-class.md), kendiniz gerekli bayt sırası dönüştürmenin yönetmeniz gerekir. Windows Yuvaları "big-Endian" bayt sırası modeli standart hale getirir ve bu sırada ve diğerleri arasında dönüştürme için işlevler sağlar. [CArchive](../mfc/reference/carchive-class.md), ancak, kullanabileceğiniz [CSocket](../mfc/reference/csocket-class.md), ters ("Endian") siparişin kullanır ancak `CArchive` ayrıntılarının bayt sırası dönüştürme sizin için üstlenir. Bu standart uygulamalarınızda sıralama ya da Windows Sockets bayt sırası dönüştürme işlevleri kullanarak, kodunuzu daha taşınabilir hale getirebilir.

Her iki ucunda da iletişim yazarken MFC Yuvaları kullanma için ideal bir durumdur: MFC her iki uçta kullanma. Büyük olasılıkla ihtiyaç duyacağınız bayt-kendiniz arşiv nesnesine verileri geçirmeden önce değiştirme yönetmek iletişim gibi bir FTP sunucusuna MFC olmayan uygulamalar ile bir uygulama yazıyorsanız Windows Sockets dönüştürme rutinleri kullanarak**ntohs**, **ntohl**, **htons**, ve **htonl**. MFC olmayan uygulama ile iletişim kurulurken kullanılan bu işlevler bir örneği, bu makalenin sonraki bölümlerinde görünür.

> [!NOTE]
>  Bir iletişim sonuna bir MFC uygulaması olmadığında, ayrıca türetilen C++ nesnelerinin akış kaçınmalısınız `CObject` , arşiv içine olduğundan alıcı işlemeye mümkün olmayacaktır. ' Ündeki nota bakın [Windows Yuvaları: yuvaların arşivlerle kullanma](../mfc/windows-sockets-using-sockets-with-archives.md).

Bayt hakkında daha fazla bilgi için bkz: Windows SDK'da bulunan Windows yuva belirtimi.

## <a name="a-byte-order-conversion-example"></a>Bayt sırası dönüştürme örneği

Aşağıdaki örnek, bir seri hale getirme işlevi için gösterir. bir `CSocket` bir arşiv kullanan nesne. Bayt sırası dönüştürme işlevleri Windows Sockets API'si kullanarak gösterilmektedir.

Bu örnekte, kaynak kodu erişimi olan bir MFC olmayan sunucu uygulaması ile iletişim kuran istemci yazmakta olduğunuz bir senaryo gösterir. Bu senaryoda, MFC olmayan sunucunun standart ağ bayt sırası kullandığını varsaymalısınız. Buna karşılık, MFC istemci uygulamanızın kullandığı bir `CArchive` nesnesi ile bir `CSocket` nesnesi ve `CArchive` "little Endian" bayt sırası, standart ağ tersini kullanır.

MFC olmayan sunucu ile iletişim kurmak planlama aşağıdakine benzer bir ileti paketi için yerleşik bir protokol sahip olduğunu varsayın:

[!code-cpp[NVC_MFCSimpleSocket#5](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_1.cpp)]

MFC bağlamında, bu gibi ifade:

[!code-cpp[NVC_MFCSimpleSocket#6](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_2.cpp)]

C++ ' ta bir **yapı** aslında bir sınıf olarak aynı işe yarar. `Message` Yapısına sahip olabilir, üye işlevleri gibi `Serialize` yukarıda bildirilen üye işlev. `Serialize` Üye işlevi şöyle görünebilir:

[!code-cpp[NVC_MFCSimpleSocket#7](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_3.cpp)]

Olduğundan Temizle uyuşmazlığı bayt MFC olmayan sunucu uygulamasının bir ucunda sıralama arasında veri bayt sırası dönüştürmeleri için bu örneği çağırır ve `CArchive` diğer ucundaki MFC istemci uygulamasında kullanılır. Örnek, çeşitli Windows Sockets sağlayan bayt sırası dönüştürme işlevleri gösterir. Aşağıdaki tabloda, bu işlevler açıklanmaktadır.

### <a name="windows-sockets-byte-order-conversion-functions"></a>Windows Yuvaları: bayt sırası dönüştürme işlevleri

|İşlev|Amaç|
|--------------|-------------|
|**ntohs**|16-bit miktarı konak bayt sırası (büyük-Endian Endian için) ağ bayt sırası Dönüştür.|
|**ntohl**|Bir 32-bit miktarı konak bayt sırası (büyük-Endian Endian için) ağ bayt sırası Dönüştür.|
|**Htons**|16-bit miktarı konak bayt sırası izlenecek ağ bayt sırası (Endian için büyük Endian) dönüştürün.|
|**Htonl**|Bir 32-bit miktarı konak bayt sırası izlenecek ağ bayt sırası (Endian için büyük Endian) dönüştürün.|

Bu örnekte başka bir noktası iletişimi diğer ucundaki yuva uygulama bir MFC olmayan uygulama olduğunda, aşağıdaki gibi yapmaktan kaçının gerekir şöyledir:

`ar << pMsg;`

Burada `pMsg` sınıfından türetilen bir C++ nesne işaretçisidir `CObject`. Bir MFC uygulaması olsaydı olduğu gibi bu, ek MFC bilgi nesneleri ve sunucu ile ilişkilendirilen anlamayacaktır gönderir.

Daha fazla bilgi için bkz.:

- [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

- [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca Bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)

