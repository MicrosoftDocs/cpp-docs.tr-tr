---
description: 'Daha fazla bilgi edinin: Windows Yuvaları: bayt sıralaması'
title: 'Windows Yuvaları: Bayt Sıralama'
ms.date: 11/04/2016
helpviewer_keywords:
- byte order issues in sockets programming
- sockets [MFC], byte order issues
- Windows Sockets [MFC], byte order issues
ms.assetid: 8a787a65-f9f4-4002-a02f-ac25a5dace5d
ms.openlocfilehash: d143967fdcc9b4d1dac772bf0fe25b67d70aef53
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118660"
---
# <a name="windows-sockets-byte-ordering"></a>Windows Yuvaları: Bayt Sıralama

Bu makalede ve iki yardımcı makalede Windows Sockets programlamasında çeşitli sorunlar açıklanmaktadır. Bu makalede bayt sıralaması ele alınmaktadır. Şu makalelerde diğer sorunlar ele alınmıştır: [Windows Yuvaları: engelleme](../mfc/windows-sockets-blocking.md) ve [Windows Yuvaları: dizeleri dönüştürme](../mfc/windows-sockets-converting-strings.md).

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)sınıfından kullanırsanız veya türetirsiniz, bu sorunları kendiniz yönetmeniz gerekecektir. [CSocket](../mfc/reference/csocket-class.md)sınıfından kullanırsanız veya türetirsiniz, MFC bunları sizin için yönetir.

## <a name="byte-ordering"></a>Bayt sıralaması

Farklı makine mimarileri bazen verileri farklı bayt siparişleri kullanarak depolar. Örneğin, Intel tabanlı makineler, verileri Macintosh (Motorola) makinelerinde ters sırada depolar. "Little-Endian" adlı Intel baytlık sıra, ağ standardı "Big-endian" sırasının de tersidir. Aşağıdaki tabloda bu terimler açıklanmaktadır.

### <a name="big--and-little-endian-byte-ordering"></a>Büyük ve Little-Endian bayt sıralaması

|Bayt sıralama|Anlamı|
|-------------------|-------------|
|Big-Endian|En önemli bayt bir sözcüğün sol ucunda.|
|Little-Endian|En önemli bayt bir sözcüğün sağ bitişidir.|

Genellikle, ağ üzerinden gönderilen ve aldığınız veriler için bayt sırası dönüştürme konusunda endişelenmeniz gerekmez, ancak bayt emirlerini dönüştürmeniz gereken durumlar vardır.

## <a name="when-you-must-convert-byte-orders"></a>Bayt emirlerini dönüştürmeniz gerektiğinde

Aşağıdaki durumlarda bayt siparişlerini dönüştürmeniz gerekir:

- Başka bir makineye gönderdiğiniz verilerin aksine, ağ tarafından yorumlanması gereken bilgileri geçiriyoruz. Örneğin, ağın anlaşılması gereken bağlantı noktalarını ve adresleri geçirebilirsiniz.

- İletişim kurduğunuz sunucu uygulaması bir MFC uygulaması değil (ve kendisi için kaynak kodunuz yok). Bu, iki makine aynı bayt sıralamasını paylaşıyorsa, bayt sırası dönüştürmeleri için çağrı yapılır.

## <a name="when-you-do-not-have-to-convert-byte-orders"></a>Bayt siparişlerini dönüştürmeniz gerekmez

Aşağıdaki durumlarda bayt siparişlerinin dönüştürme işinin önüne aşabilirsiniz:

- Her iki uçta da makineler, baytları değiştirmemelidir ve her iki makine de aynı bayt sırasını kullanır.

- İletişim kurduğunuz sunucu bir MFC uygulamasıdır.

- İletişim kurduğunuz sunucu için kaynak kodunuz var, bu nedenle, bayt siparişlerini dönüştürmeniz gerekip gerekmediğini açıkça söyleyebilirsiniz.

- Sunucunun bağlantı noktasını MFC 'ye ekleyebilirsiniz. Bu oldukça kolaydır ve sonuç genellikle daha küçük, daha hızlı bir koddur.

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)ile çalışırken, gereken tüm bayt düzeni dönüştürmelerini kendiniz yönetmeniz gerekir. Windows yuvaları, "Big-endian" bayt düzeni modelini standartlaştırır ve bu sıra ve diğer arasında dönüştürme yapmak için işlevler sağlar. Ancak, [CSocket](../mfc/reference/csocket-class.md)Ile kullandığınız [CArchive](../mfc/reference/carchive-class.md), ters ("küçük endian") sırasını kullanır, ancak `CArchive` sizin için bayt düzeni dönüştürmelerinin ayrıntılarını alır. Uygulamalarınızda bu standart sıralamayı veya Windows Sockets bayt sırası dönüştürme işlevlerini kullanarak kodunuzu daha taşınabilir hale getirebilirsiniz.

MFC yuvalarını kullanmaya yönelik ideal durum, iletişimin iki ucunu yazarken, her iki uçta da MFC 'yi kullanmaktır. Bir FTP sunucusu gibi MFC olmayan uygulamalarla iletişim kuracak bir uygulama yazıyorsanız, bir arşiv nesnesine veri geçirmeden önce **ntohs**, **ntohl**, **hton** ve **htonl** Windows Sockets dönüştürme yordamlarını kullanarak bayt değiştirmeyi kendiniz de yönetmeniz gerekir. MFC olmayan bir uygulamayla iletişim kurmak için kullanılan bu işlevlere örnek olarak bu makalenin ilerleyen kısımlarında yer alır.

> [!NOTE]
> İletişimin diğer sonu bir MFC uygulaması olmadığında, `CObject` alıcı onları işleyemeyeceği için arşivinizden türetilmiş C++ nesnelerinin akışını da önlemeniz gerekir. Bkz. [Windows Yuvaları: Arşivlerle yuvalar kullanma](../mfc/windows-sockets-using-sockets-with-archives.md).

Bayt emirleri hakkında daha fazla bilgi için, Windows SDK bulunan Windows Yuvaları belirtimine bakın.

## <a name="a-byte-order-conversion-example"></a>Byte-Order dönüştürme örneği

Aşağıdaki örnek, bir arşivi kullanan bir nesne için bir serileştirme işlevi gösterir `CSocket` . Ayrıca, Windows Sockets API 'sindeki bayt sırası dönüştürme işlevlerinin kullanılması gösterilmektedir.

Bu örnek, kaynak koda erişiminiz olmayan bir MFC olmayan sunucu uygulamasıyla iletişim kuran bir istemci yazarken bir senaryo gösterir. Bu senaryoda, MFC olmayan sunucunun standart ağ bayt sıralaması kullandığını varsaymalısınız. Buna karşılık, MFC istemci uygulamanız `CArchive` nesne içeren bir nesne kullanır `CSocket` ve `CArchive` ağ standardının tersini, "küçük endian" bayt sırasını kullanır.

İletişim kurmayı planladığınız MFC olmayan sunucunun aşağıdaki gibi bir ileti paketi için bir protokol olduğunu varsayalım:

[!code-cpp[NVC_MFCSimpleSocket#5](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_1.cpp)]

MFC koşullarında bu, aşağıdaki gibi ifade edilir:

[!code-cpp[NVC_MFCSimpleSocket#6](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_2.cpp)]

C++ ' da, bir **`struct`** sınıf ile temelde aynı şeydir. `Message`Yapının, `Serialize` yukarıda belirtilen üye işlevi gibi üye işlevleri olabilir. `Serialize`Üye işlevi şöyle görünebilir:

[!code-cpp[NVC_MFCSimpleSocket#7](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_3.cpp)]

Bu örnek, bir uçta MFC olmayan sunucu uygulamasının bayt sıralaması ve `CArchive` diğer UÇTAKI MFC istemci uygulamanızda kullanılan bir uyumsuzluk ile verilerin bayt düzeni dönüştürmelerini çağırır. Örnek, Windows Sockets sağladığı bayt düzeni dönüştürme işlevlerinin birkaçını göstermektedir. Aşağıdaki tabloda bu işlevler açıklanmaktadır.

### <a name="windows-sockets-byte-order-conversion-functions"></a>Windows Yuvaları Byte-Order dönüştürme Işlevleri

|İşlev|Amaç|
|--------------|-------------|
|**ntohs**|Bir 16 bit miktarı ağ bayt siparişinden ana bilgisayar bayt sırasına (Big endian ile little-endian arası) dönüştürür.|
|**ntohl**|32 bitlik bir miktarı ağ bayt siparişinden ana bilgisayar bayt sırasına (Big-endian ile little-endian) dönüştürün.|
|**Hton**|16 bit miktarı konak bayt siparişinden ağ bayt sırasına (little-endian ile Big-endian arası) dönüştürür.|
|**Htonl**|32 bitlik bir miktarı konak bayt siparişinden ağ bayt sırasına (little-endian ile Big-endian arası) dönüştürür.|

Bu örneğin başka bir noktası, iletişimin diğer ucundaki yuva uygulaması MFC olmayan bir uygulama olduğunda, aşağıdakine benzer bir şey yapmaktan kaçınmanız gerekir:

`ar << pMsg;`

`pMsg`, sınıfından türetilen C++ nesnesine yönelik bir işaretçidir `CObject` . Bu işlem, nesnelerle ilişkili ek MFC bilgilerini gönderir ve bu, bir MFC uygulaması olduğu gibi sunucu tarafından anlaşılmaz.

Daha fazla bilgi için bkz:

- [Windows Yuvaları: sınıf CAsyncSocket kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

- [Windows Yuvaları: akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: veri birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)
