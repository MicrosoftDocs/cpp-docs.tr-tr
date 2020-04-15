---
title: 'Windows Yuvaları: Yuvaları Arşivlerle Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], archives
- sockets [MFC], with archives
- archives [MFC], and Windows Sockets
- CSocket class [MFC], programming model
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
ms.openlocfilehash: 55b4f9a5412c1447fe2b3bde10cb934b91abf008
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359959"
---
# <a name="windows-sockets-using-sockets-with-archives"></a>Windows Yuvaları: Yuvaları Arşivlerle Kullanma

Bu makalede [CSocket programlama modeli](#_core_the_csocket_programming_model)açıklanır. Sınıf [CSocket,](../mfc/reference/csocket-class.md) soket desteğini [casyncSocket](../mfc/reference/casyncsocket-class.md)sınıfından daha yüksek bir soyutlama düzeyinde sağlar. `CSocket`Bir soket nesnesine ve bir MFC [CArchive](../mfc/reference/carchive-class.md) nesnesi üzerinden veri aktarmak için MFC serileştirme protokolünün bir sürümünü kullanır. `CSocket`engelleme sağlar (Windows iletilerinin arka plan işleme yönetirken) ve erişim sağlar `CArchive`, hangi ham API veya sınıf `CAsyncSocket`kullanarak kendiniz yapmak zorunda olacağını iletişimbirçok yönünü yönetir.

> [!TIP]
> Sınıfı, `CSocket` daha kullanışlı bir sürümü olarak `CAsyncSocket`tek başına kullanabilirsiniz, ancak en `CSocket` basit `CArchive` programlama modeli bir nesneyle kullanmaktır.

Arşivli soketlerin uygulanması hakkında daha fazla bilgi için [Windows Soketleri: Arşivli Soketler Nasıl Çalışır.](../mfc/windows-sockets-how-sockets-with-archives-work.md) Örneğin kod, [bkz. Windows Soketleri: İşlem sırası](../mfc/windows-sockets-sequence-of-operations.md) ve [Windows Soketleri: Arşiv kullanan Soketörneği.](../mfc/windows-sockets-example-of-sockets-using-archives.md) Soket sınıflarından kendi sınıflarınızı türeterek elde edebileceğiniz bazı işlevler hakkında bilgi için [Windows Soketleri: Soket Sınıflarından Türeyen](../mfc/windows-sockets-deriving-from-socket-classes.md)bölümüne bakın.

> [!NOTE]
> Yerleşik (MFC olmayan) sunucularla iletişim kurmak için bir MFC istemci programı yazıyorsanız, arşiv üzerinden C++ nesneleri göndermeyin. Sunucu göndermek istediğiniz nesne türlerini anlayan bir MFC uygulaması olmadığı sürece, nesnelerinizi alıp deserialize edemeyecektir. MFC olmayan uygulamalarla iletişim kurma konusunda ilgili materyaller için [Windows Soketleri: Bayt Siparişi](../mfc/windows-sockets-byte-ordering.md)makalesine de bakın.

## <a name="the-csocket-programming-model"></a><a name="_core_the_csocket_programming_model"></a>CSocket Programlama Modeli

Bir `CSocket` nesne kullanmak, birkaç MFC sınıfı nesneoluşturmayı ve ilişkilendirmeyi içerir. Aşağıdaki genel yordamda, her soket türünün farklı bir eylem gerektirdiği adım 3 dışında, her adım hem sunucu soketi hem de istemci soketi tarafından alınır.

> [!TIP]
> Çalışma zamanında, istemci uygulaması bir bağlantı aradığında sunucu uygulaması genellikle önce hazır ve "dinleme" başlar. İstemci bağlanmaya çalıştığında sunucu hazır değilse, genellikle kullanıcı uygulamasının daha sonra yeniden bağlanmayı denemesini gerektirirsiniz.

#### <a name="to-set-up-communication-between-a-server-socket-and-a-client-socket"></a>Sunucu soketi ile istemci soketi arasındaki iletişimi ayarlamak için

1. Bir [CSocket nesnesi](../mfc/reference/csocket-class.md) oluştur.

1. Altta yatan **SOCKET** tutamacını oluşturmak için nesneyi kullanın.

   Bir `CSocket` istemci nesne için, bir datagram soketi gerekmedikçe, normalde [oluşturmak](../mfc/reference/casyncsocket-class.md#create)için varsayılan parametreleri kullanmanız gerekir. Bir `CSocket` sunucu nesnesi `Create` için, aramada bir bağlantı noktası belirtmeniz gerekir.

    > [!NOTE]
    >  `CArchive`datagram soketleri ile çalışmaz. Bir datagram `CSocket` soketi için kullanmak istiyorsanız, sınıfı bir arşiv `CAsyncSocket`olmadan kullanacağınız gibi kullanmanız gerekir. Verigramları güvenilir olmadığından (gelmesi garanti edilmez ve tekrarlanabilir veya dizi dışında olabilir), bir arşiv aracılığıyla serileştirme ile uyumlu değildir. Bir serileştirme işleminin güvenilir ve sırayla tamamlanmasını beklersiniz. Bir veri gramı `CArchive` için bir nesneyle kullanmaya `CSocket` çalışırsanız, MFC iddiası başarısız olur.

1. Soket istemciyse, [CAsyncSocket'i arayın::Soket](../mfc/reference/casyncsocket-class.md#connect) nesnesini bir sunucu yuvasına bağlamak için bağlanın.

     -veya-

   Soket bir sunucuysa, [CAsyncSocket'i arayın::İstemcinin](../mfc/reference/casyncsocket-class.md#listen) bağlantı denemelerini dinlemeye başlamak için dinleyin. Bir bağlantı isteği aldıktan sonra, [CAsyncSocket](../mfc/reference/casyncsocket-class.md#accept)arayarak kabul edin::Kabul et.

    > [!NOTE]
    >  `Accept` Üye işlev, parametresi olarak `CSocket` yeni, boş bir nesneye başvuru alır. Bu nesneyi aramadan `Accept`önce oluşturmanız gerekir. Bu soket nesnesi kapsam dışına çıkarsa, bağlantı kapanır. Bu yeni `Create` soket nesnesi için aramayın.

1. [CSocketFile](../mfc/reference/csocketfile-class.md) nesnesini oluşturarak nesneyi `CSocket` onunla ilişkilendirin.

1. Verileri yüklemek (almak) veya depolamak (göndermek) için bir [CArchive](../mfc/reference/carchive-class.md) nesnesi oluşturun. Arşiv `CSocketFile` nesneile ilişkilidir.

   Datagram soketleri ile `CArchive` çalışmadığını unutmayın.

1. İstemci `CArchive` ve sunucu soketleri arasında veri aktarmak için nesneyi kullanın.

   Belirli `CArchive` bir nesnenin verileri yalnızca tek bir yönde hareket ettirdiğini unutmayın: yükleme (alma) veya depolama (gönderme) için. Bazı durumlarda, biri veri `CArchive` göndermek, diğeri bildirim almak için olmak üzere iki nesne kullanırsınız.

   Bağlantıyı kabul ettikten ve arşivi kurduktan sonra, parolaları doğrulama gibi görevleri gerçekleştirebilirsiniz.

1. Arşiv, soket dosyasını ve soket nesnelerini yok edin.

    > [!NOTE]
    >  Sınıf, `CArchive` `IsBufferEmpty` üye işlevi sınıfla `CSocket`birlikte kullanılmak üzere özel olarak sağlar. Arabellek, örneğin birden çok veri iletisi içeriyorsa, bunların tümü okunana ve arabellek temizlenene kadar döngü yapmanız gerekir. Aksi takdirde, alınacak veri olduğuna dair bir sonraki bildiriminiz süresiz olarak gecikebilir. Tüm `IsBufferEmpty` verileri aldığınızdan emin olmak için kullanın.

Windows [Soketleri: İşlemler Dizisi](../mfc/windows-sockets-sequence-of-operations.md) makalesi, bu işlemin her iki tarafını da örnek kodla gösterir.

Daha fazla bilgi için bkz.

- [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[CSocket::Oluştur](../mfc/reference/csocket-class.md#create)
