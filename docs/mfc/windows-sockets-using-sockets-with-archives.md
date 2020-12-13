---
description: 'Daha fazla bilgi edinin: Windows Yuvaları: Arşivlerle yuvaları kullanma'
title: 'Windows Yuvaları: Yuvaları Arşivlerle Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], archives
- sockets [MFC], with archives
- archives [MFC], and Windows Sockets
- CSocket class [MFC], programming model
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
ms.openlocfilehash: bd5f239a0fdcee4bf6c6141994c4ca5002bdc6b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331338"
---
# <a name="windows-sockets-using-sockets-with-archives"></a>Windows Yuvaları: Yuvaları Arşivlerle Kullanma

Bu makalede, [CSocket programlama modeli](#_core_the_csocket_programming_model)açıklanır. Sınıf [Csoketi](../mfc/reference/csocket-class.md) , sınıf [CAsyncSocket](../mfc/reference/casyncsocket-class.md)değerinden daha yüksek bir soyutlama düzeyinde yuva desteği sağlar. `CSocket` MFC [CArchive](../mfc/reference/carchive-class.md) nesnesi aracılığıyla bir yuva nesnesine ve öğesinden veri GEÇIRMEK için MFC serileştirme protokolünün bir sürümünü kullanır. `CSocket` engelleme sağlar (Windows iletilerinin arka plan işlemesini yönetirken) ve size `CArchive` Ham API veya sınıf kullanarak kendinize yönelik iletişimin pek çok yönünü yöneten ' e erişim sağlar `CAsyncSocket` .

> [!TIP]
> Sınıfının `CSocket` kendisini, daha uygun bir sürümü olarak kullanabilirsiniz `CAsyncSocket` , ancak en basit programlama modeli `CSocket` bir nesneyle birlikte kullanılır `CArchive` .

Arşivler ile yuvalar uygulamasının nasıl çalıştığı hakkında daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle birlikte yuvalar çalışma](../mfc/windows-sockets-how-sockets-with-archives-work.md). Örneğin, bkz. [Windows Yuvaları: Işlem dizisi](../mfc/windows-sockets-sequence-of-operations.md) ve [Windows Yuvaları: arşivleri kullanan yuvalar örneği](../mfc/windows-sockets-example-of-sockets-using-archives.md). Yuvalar sınıflarından kendi sınıflarınızı türeterek kullanabileceğiniz bazı işlevler hakkında daha fazla bilgi için bkz. [Windows Yuvaları: yuva sınıflarından türetme](../mfc/windows-sockets-deriving-from-socket-classes.md).

> [!NOTE]
> Oluşturulan (MFC olmayan) sunucularla iletişim kurmak için bir MFC istemci programı yazıyorsanız, arşiv aracılığıyla C++ nesneleri göndermeyin. Sunucu, göndermek istediğiniz nesne türlerini anlayan bir MFC uygulaması değilse, nesnelerinizi alamaz ve seri durumdan çıkaramaz. MFC olmayan uygulamalarla iletişim konusu ile ilgili malzemeler için [Windows Yuvaları: bayt sıralaması](../mfc/windows-sockets-byte-ordering.md)makalesine de bakın.

## <a name="the-csocket-programming-model"></a><a name="_core_the_csocket_programming_model"></a> CSocket programlama modeli

Bir `CSocket` nesnenin kullanılması, bırkaç MFC sınıfı nesnesinin oluşturulmasını ve ilişkilendirilmesini içerir. Aşağıdaki genel yordamda her bir adım, her yuva türünün farklı bir eylem gerektirdiği 3. adım dışında hem sunucu yuvası hem de istemci yuvası tarafından alınır.

> [!TIP]
> Çalışma zamanında, sunucu uygulaması genellikle önce, istemci uygulaması bir bağlantı arayan ilk olarak önce başlamaya ve "dinlemeye" başlar. İstemci bağlanmayı denediğinde sunucu hazırsanız, genellikle Kullanıcı uygulamasının daha sonra yeniden bağlanmayı denemesini gerekir.

#### <a name="to-set-up-communication-between-a-server-socket-and-a-client-socket"></a>Sunucu yuvası ile istemci yuvası arasında iletişim kurmak için

1. Bir [CSocket](../mfc/reference/csocket-class.md) nesnesi oluşturun.

1. Temel **yuva** tanıtıcısını oluşturmak için nesnesini kullanın.

   Bir `CSocket` istemci nesnesi için, bir veri birimi yuvasına ihtiyaç duymadığınız müddetçe normalde [oluşturmak](../mfc/reference/casyncsocket-class.md#create)üzere varsayılan parametreleri kullanmanız gerekir. `CSocket`Sunucu nesnesi için, çağrıda bir bağlantı noktası belirtmeniz gerekir `Create` .

    > [!NOTE]
    >  `CArchive` veri birimi yuvaları ile çalışmaz. `CSocket`Bir veri birimi yuvası için kullanmak istiyorsanız, bir arşiv olmadan, kullanacağınız sınıfı kullanmanız gerekir `CAsyncSocket` . Veri birimleri güvenilir olmadığından (gelmesi garanti edilmez ve yinelenebilir ya da sıra dışında olabilir), bir arşiv aracılığıyla serileştirme ile uyumlu değildir. Bir serileştirme işleminin güvenilir ve sıralı bir şekilde tamamlanmasını bekliyor. Bir `CSocket` `CArchive` veri birimi için bir nesneyle birlikte kullanmaya ÇALıŞıRSANıZ, mfc onaylama işlemi başarısız olur.

1. Yuva bir istemcise, yuva nesnesini bir sunucu yuvasına bağlamak için [CAsyncSocket:: Connect](../mfc/reference/casyncsocket-class.md#connect) ' i çağırın.

     -veya-

   Yuva bir sunucu ise, bir istemciden gelen bağlanma girişimlerini dinlemeye başlamak için [CAsyncSocket:: Listen](../mfc/reference/casyncsocket-class.md#listen) ' ı çağırın. Bir bağlantı isteği aldıktan sonra, [CAsyncSocket:: Accept](../mfc/reference/casyncsocket-class.md#accept)öğesini çağırarak kabul edin.

    > [!NOTE]
    >  `Accept`Üye işlevi, parametresi olarak yeni, boş bir nesneye başvuru alır `CSocket` . Bu nesneyi, çağrısından önce oluşturmanız gerekir `Accept` . Bu yuva nesnesi kapsam dışına geçtiğinde bağlantı kapanır. `Create`Bu yeni yuva nesnesi için çağrı kullanmayın.

1. Nesneyi onunla ilişkilendirerek bir [CSocketFile](../mfc/reference/csocketfile-class.md) nesnesi oluşturun `CSocket` .

1. Veri yükleme (alma) veya depolama (gönderme) için bir [CArchive](../mfc/reference/carchive-class.md) nesnesi oluşturun. Arşiv `CSocketFile` nesneyle ilişkili.

   `CArchive`Veri birimi yuvaları ile çalışmadığını aklınızda bulundurun.

1. `CArchive`İstemci ve sunucu yuvaları arasında veri geçirmek için nesnesini kullanın.

   Belirli bir `CArchive` nesnenin verileri yalnızca tek bir yönde taşıdığını aklınızda bulundurun: yükleme (alma) veya depolama (gönderme). Bazı durumlarda, `CArchive` bir tane olmak üzere iki nesne kullanacaksınız: biri veri göndermek için, diğeri de bildirimleri almak için kullanılır.

   Bir bağlantıyı kabul ettikten ve arşivi ayarladıktan sonra, bu gibi görevleri parola doğrulama olarak gerçekleştirebilirsiniz.

1. Arşivi, yuva dosyasını ve yuva nesnelerini yok edin.

    > [!NOTE]
    >  Sınıfı `CArchive` , `IsBufferEmpty` özellikle sınıfı ile kullanmak için üye işlevini sağlar `CSocket` . Arabellekte birden çok veri iletisi varsa, bunların tümü okunana kadar ve arabellek temizlenene kadar döngü yapmanız gerekir. Aksi takdirde, alınacak verilerin bulunduğu sonraki bildirime süresiz olarak geciktirilebilir. `IsBufferEmpty`Tüm verileri almanızı güvence altına almak için kullanın.

[Windows Yuvaları: Işlem dizisi](../mfc/windows-sockets-sequence-of-operations.md) , bu işlemin her iki tarafını da örnek kodla gösterir.

Daha fazla bilgi için bkz:

- [Windows Yuvaları: akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: veri birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[CSocket:: Create](../mfc/reference/csocket-class.md#create)
