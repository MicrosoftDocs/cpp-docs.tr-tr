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
ms.openlocfilehash: 3977308776c4ec6fed844038c4453ad03d065f98
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445946"
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma

Bu makalede, [CAsyncSocket](../mfc/reference/casyncsocket-class.md)sınıfının nasıl kullanılacağı açıklanmaktadır. Bu sınıfın Windows Sockets API 'sini çok düşük bir düzeyde Kapsüller unutmayın. `CAsyncSocket`, ağ iletişimini ayrıntılı olarak bilen ancak ağ olaylarının bildirilmesi için geri çağırmaların rahatlığını sağlayan programcılar tarafından kullanım içindir. Bu varsayım temelinde, bu makalede yalnızca temel yönerge sunulmaktadır. Windows Sockets 'in bir MFC uygulamasında birden çok ağ protokolle ilgilenme kolaylığını tercih etmek, ancak esneklik sağlamak istemiyorsanız `CAsyncSocket` kullanmayı göz önünde bulundurmanız gerekir. Ayrıca, `CSocket`sınıfının daha genel alternatif modelini kullanmaktan daha doğrudan iletişim başlatarak daha fazla verimlilik sağlayabilirsiniz.

`CAsyncSocket` *MFC başvurusunda*belgelenmiştir. Görsel C++ , Windows SDK bulunan Windows Yuvaları belirtimini de sağlar. Ayrıntılar size ayrıldı. Visual C++ , `CAsyncSocket`için örnek bir uygulama sağlamaz.

Ağ iletişimleri hakkında çok bilgi sahibi değilseniz ve basit bir çözüm istiyorsanız, `CArchive` nesnesi ile sınıf [Csoketi](../mfc/reference/csocket-class.md) kullanın. Daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle yuvaları kullanma](../mfc/windows-sockets-using-sockets-with-archives.md) .

Bu makalede ele alınmıştır:

- `CAsyncSocket` nesnesi oluşturma ve kullanma.

- [CAsyncSocket ile sorumluluklarınız](#_core_your_responsibilities_with_casyncsocket).

##  <a name="_core_creating_and_using_a_casyncsocket_object"></a>CAsyncSocket nesnesi oluşturma ve kullanma

#### <a name="to-use-casyncsocket"></a>CAsyncSocket kullanmak için

1. Bir [CAsyncSocket](../mfc/reference/casyncsocket-class.md) nesnesi oluşturun ve temel alınan **yuva** tanıtıcısını oluşturmak için nesnesini kullanın.

   Bir yuvanın oluşturulması, iki aşamalı oluşturma MFC deseninin izlediği bir yuva izler.

   Örnek:

   [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]

     -veya-

   [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]

   Yukarıdaki ilk Oluşturucu yığında bir `CAsyncSocket` nesnesi oluşturur. İkinci Oluşturucu yığında bir `CAsyncSocket` oluşturur. Yukarıdaki ilk [oluşturma](../mfc/reference/casyncsocket-class.md#create) çağrısı, akış yuvası oluşturmak için varsayılan parametreleri kullanır. İkinci `Create` çağrısı, belirtilen bağlantı noktası ve adresle bir veri birimi yuvası oluşturur. (Yapı yöntemiyle birlikte `Create` sürümünü kullanabilirsiniz.)

   `Create` parametreler şunlardır:

   - Bir "bağlantı noktası": kısa bir tamsayı.

      Sunucu yuvası için bir bağlantı noktası belirtmeniz gerekir. Bir istemci yuvasında genellikle bu parametre için varsayılan değeri kabul etmiş olursunuz ve bu, Windows Sockets 'in bir bağlantı noktası seçmesini sağlar.

   - Yuva türü: **sock_stream** (varsayılan) veya **sock_dgram**.

   - "Ftp.microsoft.com" veya "128.56.22.8" gibi bir yuva "adres".

      Bu, ağdaki Internet Protokolü (IP) adresidir. Muhtemelen bu parametre için varsayılan değere her zaman güvenirsiniz.

   "Bağlantı noktası" ve "yuva adresi" terimleri [Windows Yuvaları: bağlantı noktaları ve yuva adresleri](../mfc/windows-sockets-ports-and-socket-addresses.md)bölümünde açıklanmaktadır.

1. Yuva bir istemcise, [CAsyncSocket:: Connect](../mfc/reference/casyncsocket-class.md#connect)kullanarak yuva nesnesini bir sunucu yuvasına bağlayın.

     -veya-

   Yuva bir sunucu ise, bir istemciden gelen bağlantı girişimleri için dinlemeyi başlamaya ( [CAsyncSocket:: Listen](../mfc/reference/casyncsocket-class.md#listen)) ayarlayın. Bir bağlantı isteği aldıktan sonra, [CAsyncSocket:: Accept](../mfc/reference/casyncsocket-class.md#accept)ile bunu kabul edin.

   Bir bağlantıyı kabul ettikten sonra, bu gibi görevleri parola doğrulama olarak gerçekleştirebilirsiniz.

    > [!NOTE]
    >  `Accept` member işlevi, parametresi olarak yeni, boş bir `CSocket` nesnesine bir başvuru alır. `Accept`çağırmadan önce bu nesneyi oluşturmanız gerekir. Bu yuva nesnesi kapsam dışına geçtiğinde bağlantı kapanır. Bu yeni yuva nesnesi için `Create` çağırmayın. Bir örnek için bkz. [Windows Yuvaları: Işlem dizisi](../mfc/windows-sockets-sequence-of-operations.md).

1. Windows Sockets API işlevlerini kapsülleyen `CAsyncSocket` nesnenin üye işlevlerini çağırarak diğer yuvalarla iletişim gerçekleştirin.

   *MFC başvurusunda*Windows Yuvaları belirtimi ve sınıf [CAsyncSocket](../mfc/reference/casyncsocket-class.md) sınıfına bakın.

1. `CAsyncSocket` nesnesini yok edin.

   Eğer yuva nesnesini yığında oluşturduysanız, kapsayıcı işlevi kapsam dışına geçtiğinde yıkıcısı çağırılır. **New** işlecini kullanarak öbek üzerinde yuva nesnesini oluşturduysanız, nesneyi yok etmek için **Delete** işlecini kullanmaktan siz sorumlusunuz.

   Yıkıcı, nesneyi yok etmeden önce nesnenin [Close](../mfc/reference/casyncsocket-class.md#close) üye işlevini çağırır.

Koddaki bu dizi bir örnek için (aslında `CSocket` nesnesi için) bkz. [Windows Yuvaları: Işlem dizisi](../mfc/windows-sockets-sequence-of-operations.md).

##  <a name="_core_your_responsibilities_with_casyncsocket"></a>CAsyncSocket ile sorumluluklar

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)sınıfından bir nesne oluşturduğunuzda, nesne bir Windows **yuva** tutamacı kapsüller ve bu tanıtıcı üzerinde işlemler sağlar. `CAsyncSocket`kullandığınızda, API 'YI doğrudan kullanıyorsanız yüz yüze olabileceğiniz tüm sorunlar ile uğraşmanız gerekir. Örnek:

- "Engelleyici" senaryolar.

- Gönderen ve alan makineler arasındaki bayt sırası farklılıkları.

- Unicode ve çok baytlı karakter kümesi (MBCS) dizeleri arasında dönüştürme.

Bu koşulların ve ek bilgilerin tanımları için bkz. [Windows Yuvaları: engelleme](../mfc/windows-sockets-blocking.md), [Windows Yuvaları: bayt sıralaması](../mfc/windows-sockets-byte-ordering.md), [Windows Yuvaları: dizeleri dönüştürme](../mfc/windows-sockets-converting-strings.md).

Bu sorunlar söz konusu olduğunda, uygulamanız sizin için gerekli olan tüm esnekliği ve denetimleri gerektiriyorsa, sınıf `CAsycnSocket` sizin için doğru seçim olabilir. Aksi takdirde, bunun yerine sınıf `CSocket` kullanmayı göz önünde bulundurmanız gerekir. `CSocket`, sizin için çok sayıda ayrıntıyı gizler: Bu, engelleme çağrıları sırasında Windows iletileri elde edin ve size, size ait bayt sırası farklarını ve dize dönüştürmeyi yöneten `CArchive`erişmenizi sağlar.

Daha fazla bilgi için bkz.

- [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

- [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)
