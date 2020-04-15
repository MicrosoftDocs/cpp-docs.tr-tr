---
title: "Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma"
ms.date: 11/04/2016
helpviewer_keywords:
- CAsyncSocket class [MFC], programming model
- Windows Sockets [MFC], asynchronous
- sockets [MFC], converting between Unicode and MBCS strings
- SOCKET handle
- sockets [MFC], asynchronous operation
- Windows Sockets [MFC], converting Unicode and MBCS strings
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
ms.openlocfilehash: d3fc32d9da54d9cf8c79e9e5de45b81c2ef64a6e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371964"
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma

Bu makalede, [casyncSocket](../mfc/reference/casyncsocket-class.md)sınıfının nasıl kullanılacağı açıklanmaktadır. Bu sınıfın Windows Soketleri API'sini çok düşük bir düzeyde kapsüllediğini unutmayın. `CAsyncSocket`ağ iletişimini ayrıntılı olarak bilen ancak ağ olaylarının bildirilmesi için geri arama kolaylığı isteyen programcılar tarafından kullanım içindir. Bu varsayıma dayanarak, bu makalede yalnızca temel yönerge sağlar. Windows Soketleri'nin bir MFC uygulamasında birden çok ağ protokolüyle başa çıkma kolaylığı istiyorsanız, ancak esneklikkullanmaktan ödün vermek istemiyorsanız, büyük olasılıkla kullanmayı `CAsyncSocket` düşünmelisiniz. Ayrıca, daha genel alternatif sınıf `CSocket`modelini kullanarak iletişimi daha doğrudan kendiniz programlayarak daha iyi verimlilik elde edebileceğinizi hissedebilirsiniz.

`CAsyncSocket`*MFC Başvurusu'nda*belgelenmiştir. Visual C++, Windows SDK'da bulunan Windows Soketleri belirtimini de sağlar. Detaylar size bırakılmış. Visual C++ için `CAsyncSocket`örnek bir uygulama sağlamaz.

Ağ iletişimi hakkında son derece bilgili değilseniz ve basit bir `CArchive` çözüm istiyorsanız, [cSocket](../mfc/reference/csocket-class.md) sınıfı bir nesneyle kullanın. Bkz. Windows Soketleri: Daha fazla bilgi için [Arşivli Soketleri Kullanma.](../mfc/windows-sockets-using-sockets-with-archives.md)

Bu makale şunları kapsamaktadır:

- Nesne `CAsyncSocket` oluşturma ve kullanma.

- [CAsyncSocket ile sorumluluklarınız.](#_core_your_responsibilities_with_casyncsocket)

## <a name="creating-and-using-a-casyncsocket-object"></a><a name="_core_creating_and_using_a_casyncsocket_object"></a>CAsyncSocket Nesneoluşturma ve Kullanma

#### <a name="to-use-casyncsocket"></a>CAsyncSocket kullanmak için

1. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) nesnesi oluşturun ve altta yatan **SOCKET** tutamacını oluşturmak için nesneyi kullanın.

   Bir soket oluşturulması, iki aşamalı yapının MFC desenini izler.

   Örneğin:

   [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]

     -veya-

   [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]

   Yukarıdaki ilk oluşturucu yığında bir `CAsyncSocket` nesne oluşturur. İkinci yapıcı yığın üzerinde `CAsyncSocket` bir oluşturur. Yukarıdaki ilk [Create](../mfc/reference/casyncsocket-class.md#create) araması, bir akış soketi oluşturmak için varsayılan parametreleri kullanır. İkinci `Create` arama, belirli bir bağlantı noktası ve adresi olan bir veri gramsoketi oluşturur. (Her iki `Create` sürümü de inşaat yöntemiyle kullanabilirsiniz.)

   Parametreler şunlardır: `Create`

   - Bir "bağlantı noktası": kısa bir tamsayı.

      Bir sunucu soketi için bir bağlantı noktası belirtmeniz gerekir. İstemci yuvası için, windows soketlerinin bir bağlantı noktası seçmesine olanak tanıyan bu parametrenin varsayılan değerini genellikle kabul eylesiniz.

   - Soket türü: **SOCK_STREAM** (varsayılan) veya **SOCK_DGRAM.**

   - "ftp.microsoft.com" veya "128.56.22.8" gibi bir soket "adresi".

      Bu, ağdaki Internet Protokolü (IP) adresinizdir. Büyük olasılıkla her zaman bu parametre için varsayılan değere güvenirsiniz.

   "Bağlantı noktası" ve "soket adresi" terimleri [Windows Soketlerinde açıklanmıştır: Bağlantı noktaları ve Soket Adresleri.](../mfc/windows-sockets-ports-and-socket-addresses.md)

1. Soket istemciyse, [CAsyncSocket kullanarak](../mfc/reference/casyncsocket-class.md#connect)soket nesnesini bir sunucu soketine bağlayın::Bağlanın.

     -veya-

   Soket bir sunucuysa, istemciden gelen bağlantı girişimleri için soketi dinlemeye başlayacak şekilde ayarlayın [(CAsyncSocket ile::Dinle).](../mfc/reference/casyncsocket-class.md#listen) Bir bağlantı isteği aldıktan sonra, [CAsyncSocket](../mfc/reference/casyncsocket-class.md#accept)ile kabul edin::Kabul edin.

   Bir bağlantıyı kabul ettikten sonra, parolaları doğrulama gibi görevleri gerçekleştirebilirsiniz.

    > [!NOTE]
    >  `Accept` Üye işlev, parametresi olarak `CSocket` yeni, boş bir nesneye başvuru alır. Bu nesneyi aramadan `Accept`önce oluşturmanız gerekir. Bu soket nesnesi kapsam dışına çıkarsa, bağlantı kapanır. Bu yeni `Create` soket nesnesi için aramayın. Örneğin, [Windows Soketleri: İşlemler Dizisi makalesine](../mfc/windows-sockets-sequence-of-operations.md)bakın.

1. Windows Soketleri API işlevlerini `CAsyncSocket` kapsülleyen nesnenin üye işlevlerini çağırarak diğer soketlerle iletişimi gerçekleştirin.

   *MFC Başvurusu'ndaki*Windows Soketleri belirtimine ve [casyncSocket sınıfına](../mfc/reference/casyncsocket-class.md) bakın.

1. Nesneyi `CAsyncSocket` yok et.

   Yığındaki soket nesnesini oluşturduysanız, içeren işlev kapsam dışına çıktığında yıkıcısı çağrılır. Yeni **işleci** kullanarak yığındaki soket nesnesini oluşturduysanız, nesneyi yok etmek için **silme** işlecinin kullanılmasından siz sorumlusunuz.

   Yıkıcı nesneyi yok etmeden önce nesnenin [Yakın](../mfc/reference/casyncsocket-class.md#close) üye işlevini çağırır.

Koddaki bu dizinin bir örneği için `CSocket` (aslında bir nesne için), [bkz.](../mfc/windows-sockets-sequence-of-operations.md)

## <a name="your-responsibilities-with-casyncsocket"></a><a name="_core_your_responsibilities_with_casyncsocket"></a>CAsyncSocket ile Sorumluluklarınız

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)sınıfıbir nesne oluşturduğunuzda, nesne bir Windows **SOCKET** tutamacını kapsüller ve bu tutamaç üzerinde işlem sağlar. Kullandığınızda, `CAsyncSocket`API'yi doğrudan kullanıyorsanız karşılaşabileceğiniz tüm sorunlarla ilgilenmeniz gerekir. Örneğin:

- "Engelleme" senaryoları.

- Gönderme ve alma makineleri arasındaki bayt sipariş farkları.

- Unicode ve multibayt karakter kümesi (MBCS) dizeleri arasında dönüştürme.

Bu terimlerin ve ek bilgilerin tanımları için [bkz: Windows Soketleri: Engelleme,](../mfc/windows-sockets-blocking.md) [Windows Soketleri: Bayt Sıralama,](../mfc/windows-sockets-byte-ordering.md) [Windows Soketleri: Dizeleri dönüştürme.](../mfc/windows-sockets-converting-strings.md)

Bu sorunlara rağmen, uygulamanız alabileceğiniz tüm esnekliği ve denetimi gerektiriyorsa, sınıf `CAsycnSocket` sizin için doğru seçim olabilir. Değilse, bunun yerine sınıf `CSocket` kullanmayı düşünmelisiniz. `CSocket`sizden çok fazla ayrıntı gizler: aramaları engelleme sırasında Windows iletileri pompalar ve erişim sağlar `CArchive`, hangi sizin için bayt sipariş farklılıkları ve dize dönüşüm yönetir.

Daha fazla bilgi için bkz.

- [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

- [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)
