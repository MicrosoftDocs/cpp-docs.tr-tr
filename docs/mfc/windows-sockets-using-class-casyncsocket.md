---
description: 'Daha fazla bilgi edinin: Windows Yuvaları: sınıf CAsyncSocket kullanma'
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
ms.openlocfilehash: 9fbf385a2e327588685fdcb996465386628e5e4d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118608"
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma

Bu makalede, [CAsyncSocket](../mfc/reference/casyncsocket-class.md)sınıfının nasıl kullanılacağı açıklanmaktadır. Bu sınıfın Windows Sockets API 'sini çok düşük bir düzeyde Kapsüller unutmayın. `CAsyncSocket` , ağ iletişimini ayrıntılı olarak bilen ancak ağ olaylarının bildirilmesi için geri çağırmaların rahatlığını isteyen programcılar tarafından kullanılabilir. Bu varsayım temelinde, bu makalede yalnızca temel yönerge sunulmaktadır. Büyük olasılıkla, `CAsyncSocket` BIR MFC uygulamasında birden çok ağ protokolleriyle Ilgili Windows Yuvaları kullanımı kolaylığını tercih ediyorsanız ancak esnekliği Fede etmek istemediğiniz durumlarda kullanmayı göz önünde bulundurmanız gerekir. Ayrıca, daha genel alternatif modeli kullanarak iletişimleri daha doğrudan programlayarak daha iyi bir verimlilik alabilir `CSocket` .

`CAsyncSocket`*MFC başvurusunda* belgelenmiştir. Visual C++ Ayrıca, Windows SDK bulunan Windows Yuvaları belirtimini de sağlar. Ayrıntılar size ayrıldı. Visual C++ için örnek bir uygulama sağlamaz `CAsyncSocket` .

Ağ iletişimleri hakkında çok bilgi sahibi değilseniz ve basit bir çözüm istiyorsanız, bir nesneyle sınıf [Csoketi](../mfc/reference/csocket-class.md) kullanın `CArchive` . Daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle yuvaları kullanma](../mfc/windows-sockets-using-sockets-with-archives.md) .

Bu makalede şunları ele alınmaktadır:

- Bir nesnesi oluşturma ve kullanma `CAsyncSocket` .

- [CAsyncSocket ile sorumluluklarınız](#_core_your_responsibilities_with_casyncsocket).

## <a name="creating-and-using-a-casyncsocket-object"></a><a name="_core_creating_and_using_a_casyncsocket_object"></a> CAsyncSocket nesnesi oluşturma ve kullanma

#### <a name="to-use-casyncsocket"></a>CAsyncSocket kullanmak için

1. Bir [CAsyncSocket](../mfc/reference/casyncsocket-class.md) nesnesi oluşturun ve temel alınan **yuva** tanıtıcısını oluşturmak için nesnesini kullanın.

   Bir yuvanın oluşturulması, iki aşamalı oluşturma MFC deseninin izlediği bir yuva izler.

   Örneğin:

   [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]

     -veya-

   [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]

   Yukarıdaki ilk Oluşturucu `CAsyncSocket` yığında bir nesne oluşturur. İkinci Oluşturucu yığında bir oluşturur `CAsyncSocket` . Yukarıdaki ilk [oluşturma](../mfc/reference/casyncsocket-class.md#create) çağrısı, akış yuvası oluşturmak için varsayılan parametreleri kullanır. İkinci `Create` çağrı, belirtilen bağlantı noktası ve adresle bir veri birimi yuvası oluşturur. ( `Create` Yapı yöntemiyle iki sürümü de kullanabilirsiniz.)

   Parametreleri `Create` :

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
    >  `Accept`Üye işlevi, parametresi olarak yeni, boş bir nesneye başvuru alır `CSocket` . Bu nesneyi, çağrısından önce oluşturmanız gerekir `Accept` . Bu yuva nesnesi kapsam dışına geçtiğinde bağlantı kapanır. `Create`Bu yeni yuva nesnesi için çağrı kullanmayın. Bir örnek için bkz. [Windows Yuvaları: Işlem dizisi](../mfc/windows-sockets-sequence-of-operations.md).

1. `CAsyncSocket`Windows SOCKETS API işlevlerini kapsülleyen nesnenin üye işlevlerini çağırarak diğer yuvalarla iletişim gerçekleştirin.

   *MFC başvurusunda* Windows Yuvaları belirtimi ve sınıf [CAsyncSocket](../mfc/reference/casyncsocket-class.md) sınıfına bakın.

1. Nesneyi yok edin `CAsyncSocket` .

   Eğer yuva nesnesini yığında oluşturduysanız, kapsayıcı işlevi kapsam dışına geçtiğinde yıkıcısı çağırılır. İşleci kullanarak öbek üzerinde yuva nesnesini oluşturduysanız, **`new`** **`delete`** nesneyi yok etmek için işlecini kullanmaktan sorumlusunuz.

   Yıkıcı, nesneyi yok etmeden önce nesnenin [Close](../mfc/reference/casyncsocket-class.md#close) üye işlevini çağırır.

Bu dizi kodda (aslında bir nesne için) bir örnek için `CSocket` bkz. [Windows Yuvaları: işlem dizisi](../mfc/windows-sockets-sequence-of-operations.md).

## <a name="your-responsibilities-with-casyncsocket"></a><a name="_core_your_responsibilities_with_casyncsocket"></a> CAsyncSocket ile sorumluluklar

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)sınıfından bir nesne oluşturduğunuzda, nesne bir Windows **yuva** tutamacı kapsüller ve bu tanıtıcı üzerinde işlemler sağlar. Kullandığınızda `CAsyncSocket` , API 'yi doğrudan kullanıyorsanız yüz yüze olabileceğiniz tüm sorunları uygulamanız gerekir. Örneğin:

- "Engelleyici" senaryolar.

- Gönderen ve alan makineler arasındaki bayt sırası farklılıkları.

- Unicode ve çok baytlı karakter kümesi (MBCS) dizeleri arasında dönüştürme.

Bu koşulların ve ek bilgilerin tanımları için bkz. [Windows Yuvaları: engelleme](../mfc/windows-sockets-blocking.md), [Windows Yuvaları: bayt sıralaması](../mfc/windows-sockets-byte-ordering.md), [Windows Yuvaları: dizeleri dönüştürme](../mfc/windows-sockets-converting-strings.md).

Bu sorunlara karşın, `CAsycnSocket` uygulamanız sizin için uygun olan tüm esnekliği ve denetimleri gerektiriyorsa, sınıf sizin için doğru seçim olabilir. Aksi takdirde, bunun yerine sınıfını kullanmayı göz önünde bulundurmanız gerekir `CSocket` . `CSocket` sizin için çok sayıda ayrıntıyı gizler: Bu, engelleme çağrıları sırasında Windows iletileri elde etmenizi sağlar ve `CArchive` size, sizin için bayt sırası farklarını ve dize dönüştürmeyi yönetir.

Daha fazla bilgi için bkz:

- [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

- [Windows Yuvaları: akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: veri birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)
