---
title: 'Windows Yuvaları: Bayt Sıralama'
ms.date: 11/04/2016
helpviewer_keywords:
- byte order issues in sockets programming
- sockets [MFC], byte order issues
- Windows Sockets [MFC], byte order issues
ms.assetid: 8a787a65-f9f4-4002-a02f-ac25a5dace5d
ms.openlocfilehash: 50548202483c4d9d4471ad2c600270c4df4503e7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371058"
---
# <a name="windows-sockets-byte-ordering"></a>Windows Yuvaları: Bayt Sıralama

Bu makale ve iki yardımcı makale, Windows Soketleri programlamaçeşitli sorunları açıklar. Bu makalede bayt siparişi yer alıyor. Diğer konular makalelerde ele alınmıştır: [Windows Soketleri: Engelleme](../mfc/windows-sockets-blocking.md) ve [Windows Soketleri: Dizeleri dönüştürme.](../mfc/windows-sockets-converting-strings.md)

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)sınıfı kullanıyor veya bu türlerden türetilmiştir, bu sorunları kendiniz yönetmeniz gerekir. [CSocket](../mfc/reference/csocket-class.md)sınıfı kullanıyor veya bu sınıftan türetilmiştir, MFC bunları sizin için yönetir.

## <a name="byte-ordering"></a>Bayt Siparişi

Farklı makine mimarileri bazen farklı bayt siparişleri kullanarak veri depolar. Örneğin, Intel tabanlı makineler verileri Macintosh (Motorola) makinelerinin ters sırasına göre depolar. "Little-Endian" adı verilen Intel bayt sırası, ağ standardı "big-Endian" siparişinin de tersidir. Aşağıdaki tabloda bu terimler açıklanmaktadır.

### <a name="big--and-little-endian-byte-ordering"></a>Büyük ve Little-Endian Bayt Sipariş

|Bayt sıralama|Anlamı|
|-------------------|-------------|
|Büyük Endian|En önemli bayt bir sözcüğün sol ucundadır.|
|Küçük Endian|En önemli bayt bir sözcüğün sağ ucundadır.|

Genellikle, ağ üzerinden gönderdiğiniz ve aldığınız veriler için bayt siparişi dönüştürme konusunda endişelenmenize gerek yoktur, ancak bayt siparişlerini dönüştürmeniz gereken durumlar vardır.

## <a name="when-you-must-convert-byte-orders"></a>Bayt Siparişlerini Dönüştürmeniz Gerektiğinde

Aşağıdaki durumlarda bayt siparişlerini dönüştürmeniz gerekir:

- Başka bir makineye gönderdiğiniz verilerin aksine, ağ tarafından yorumlanması gereken bilgileri aktarıyorsun. Örneğin, ağın anlaması gereken bağlantı noktalarını ve adreslerini geçebilirsiniz.

- İletişim kurduğunuz sunucu uygulaması bir MFC uygulaması değildir (ve bunun için kaynak kodunuz yoktur). Bu, iki makine aynı bayt siparişini paylaşmazsa bayt sipariş ideşlerini çağırır.

## <a name="when-you-do-not-have-to-convert-byte-orders"></a>Byte Siparişlerini Dönüştürmek Zorunda Olmadığınız Zaman

Aşağıdaki durumlarda bayt siparişlerini dönüştürme işini önleyebilirsiniz:

- Her iki uçtaki makineler bayt ları değiştirmeme konusunda anlaşabiliyor ve her iki makine de aynı bayt siparişini kullanıyor.

- İletişim kurduğunuz sunucu bir MFC uygulamasıdır.

- İletişim kurduğunuz sunucu için kaynak kodunuz vardır, böylece bayt siparişlerini dönüştürmeniz gerekip gerekmediğini açıkça anlayabilirsiniz.

- Sunucuyu MFC'ye taşınabilirsiniz. Bunu yapmak oldukça kolaydır ve sonuç genellikle daha küçük, daha hızlı koddur.

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)ile çalışarak, gerekli bayt sipariş dönüşümlerini kendiniz yönetmelisiniz. Windows Soketleri "big-Endian" bayt siparişi modelini standartlaştırır ve bu sipariş le diğerleri arasında dönüştürmek için işlevler sağlar. [CArchive](../mfc/reference/carchive-class.md), ancak, [CSocket](../mfc/reference/csocket-class.md)ile kullandığınız, tam tersi ("little-Endian") sipariş kullanır, ancak `CArchive` sizin için bayt sipariş dönüşümleri ayrıntıları ilgilenir. Uygulamalarınızda bu standart sıralamayı kullanarak veya Windows Sockets bayt siparişi dönüştürme işlevlerini kullanarak kodunuzu daha taşınabilir hale getirebilirsiniz.

MFC soketlerini kullanmak için ideal durum, iletişimin her iki ucunu da yazarken: Her iki uçta da MFC kullanmak. FtP sunucusu gibi MFC olmayan uygulamalarla iletişim kuracak bir uygulama yazıyorsanız, windows sockets dönüşüm yordamlarını kullanarak arşiv nesnesine veri aktarmadan önce büyük olasılıkla bayt değiştirme işlemini yönetmeniz gerekir, windows soketleri dönüştürme yordamları **ntohs**, **ntohl**, **htons**, ve **htonl**. MFC olmayan bir uygulamayla iletişim kurmak için kullanılan bu işlevlerin bir örneği bu makalede daha sonra görünür.

> [!NOTE]
> İletişimin diğer ucu bir MFC uygulaması değilse, alıcı bunları işleyemediği `CObject` için arşivinize türetilen C++ nesnelerini akışından da kaçınmalısınız. Windows Soketleri'ndeki nota [bakın: Arşivli Soketleri Kullanma.](../mfc/windows-sockets-using-sockets-with-archives.md)

Bayt siparişleri hakkında daha fazla bilgi için Windows SDK'da bulunan Windows Soketleri belirtimine bakın.

## <a name="a-byte-order-conversion-example"></a>Bayt Sipariş Dönüştürme Örneği

Aşağıdaki örnek, arşiv kullanan bir `CSocket` nesne için bir serileştirme işlevini gösterir. Ayrıca, Windows Soketleri API'sında ki bayt siparişi dönüştürme işlevlerini de gösterir.

Bu örnek, kaynak koduna erişiminiz olmayan MFC olmayan bir sunucu uygulamasıyla iletişim kuran bir istemci yazdığınız bir senaryo sunar. Bu senaryoda, MFC olmayan sunucunun standart ağ bayt siparişini kullandığını varsaymanız gerekir. Buna karşılık, MFC istemci `CArchive` uygulamanız `CSocket` nesnesi `CArchive` olan bir nesne kullanır ve ağ standardının tam tersi olan "little-Endian" bayt sırasını kullanır.

İletişim kurmayı planladığınız MFC olmayan sunucunun aşağıdaki gibi bir ileti paketi için oluşturulmuş bir protokolü olduğunu varsayalım:

[!code-cpp[NVC_MFCSimpleSocket#5](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_1.cpp)]

MFC açısından, bu aşağıdaki gibi ifade edilecektir:

[!code-cpp[NVC_MFCSimpleSocket#6](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_2.cpp)]

C++'da **yapı** aslında sınıfla aynı şeydir. Yapı, `Message` yukarıda bildirilen üye işlev `Serialize` gibi üye işlevlere sahip olabilir. `Serialize` Üye işlev aşağıdaki gibi görünebilir:

[!code-cpp[NVC_MFCSimpleSocket#7](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_3.cpp)]

Bu örnek, bir uçta MFC olmayan sunucu uygulamasının bayt siparişi ile diğer uçtaki MFC istemci uygulamanızda `CArchive` kullanılan bayt siparişi arasında açık bir uyumsuzluk olduğundan, verilerin bayt sıralı dönüşümlerini çağırır. Örnek, Windows Soketleri'nin sağladığı bayt siparişdönüştürme işlevlerinden birkaçını göstermektedir. Aşağıdaki tabloda bu işlevler açıklanmaktadır.

### <a name="windows-sockets-byte-order-conversion-functions"></a>Windows Soketleri Bayt Sırası Dönüştürme Fonksiyonları

|İşlev|Amaç|
|--------------|-------------|
|**ntohs**|Ağ bayt siparişinden 16 bitlik bir miktarı bayt siparişini (big-Endian'dan little-Endian'a) barındırmak için dönüştürün.|
|**ntohl**|32 bitlik bir miktarı ağ bayt siparişinden bayt siparişine (big-Endian to little-Endian) barındırmak için dönüştürün.|
|**Htons**|16 bitlik bir miktarı ana bilgisayar bayt siparişinden ağ bayt siparişine (little-Endian to big-Endian) dönüştürün.|
|**Htonl**|32 bitlik bir miktarı ana bilgisayar bayt siparişinden ağ bayt siparişine (little-Endian to big-Endian) dönüştürün.|

Bu örneğin bir diğer noktası, iletişimin diğer ucundaki soket uygulaması MFC olmayan bir uygulama olduğunda, aşağıdaki gibi bir şey yapmaktan kaçınmanız gerektiğidir:

`ar << pMsg;`

sınıftan `pMsg` `CObject`türetilen bir C++ nesnesine işaretçi nerede. Bu, nesnelerle ilişkili ekstra MFC bilgileri gönderir ve sunucu, bir MFC uygulaması olsaydı olduğu gibi, bunu anlamaz.

Daha fazla bilgi için bkz.

- [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

- [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)
