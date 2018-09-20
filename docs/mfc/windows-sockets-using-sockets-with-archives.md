---
title: 'Windows Yuvaları: Yuvaları Arşivlerle kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], archives
- sockets [MFC], with archives
- archives [MFC], and Windows Sockets
- CSocket class [MFC], programming model
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 217dcd1d5e999ea640795c656bbf40f7adad3d7d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398755"
---
# <a name="windows-sockets-using-sockets-with-archives"></a>Windows Yuvaları: Yuvaları Arşivlerle Kullanma

Bu makalede [CSocket programlama modeli](#_core_the_csocket_programming_model). Sınıf [CSocket](../mfc/reference/csocket-class.md) sınıfı sağladığından daha yüksek düzeyde soyutlama yuva desteği sağlayan [Casyncsocket'ini](../mfc/reference/casyncsocket-class.md). `CSocket` bir yuva nesnesi aracılığıyla bir MFC gelen ve giden veri iletmek için MFC serileştirme protokol sürümü kullanan [CArchive](../mfc/reference/carchive-class.md) nesne. `CSocket` (Windows iletilerinin arka plan işlemesi yönetirken) engelleme sunar ve aşağıdakilere erişmenizi sağlar `CArchive`, ham API veya sınıfı kullanarak kendiniz yapmak zorunda iletişim birçok yönüyle yönetir `CAsyncSocket`.

> [!TIP]
>  Sınıf kullanabileceğiniz `CSocket` kendisi daha kullanışlı bir sürümü olarak `CAsyncSocket`, ancak basit bir programlama modeli kullanmaktır `CSocket` ile bir `CArchive` nesne.

Yuvaların arşivlerle uygulamasını nasıl çalıştığı hakkında daha fazla bilgi için bkz. [Windows Yuvaları: Yuva arşivler ile nasıl](../mfc/windows-sockets-how-sockets-with-archives-work.md). Örnek kod için bkz: [Windows Yuvaları: dizisi, işlemleri](../mfc/windows-sockets-sequence-of-operations.md) ve [Windows Yuvaları: örnek, yuva kullanarak arşivleri](../mfc/windows-sockets-example-of-sockets-using-archives.md). Kendi sınıflarınızı yuva sınıflarından türetme tarafından elde işlevlerinden bazıları hakkında bilgi için bkz [Windows Yuvaları: Yuva sınıflarından türetme](../mfc/windows-sockets-deriving-from-socket-classes.md).

> [!NOTE]
>  C++ nesnelerinin arşiv aracılığıyla kurulan (MFC olmayan) sunucularıyla iletişim kurmak için bir MFC istemci programı yazıyorsanız göndermeyin. Göndermek istediğiniz nesne türlerini anlayan bir MFC uygulaması sunucu olmadığı sürece, alma ve nesnelerinizin seri durumdan mümkün olmayacaktır. MFC olmayan uygulamaları ile iletişim konuyla ilgili malzeme için Ayrıca bkz [Windows Yuvaları: bayt sıralama](../mfc/windows-sockets-byte-ordering.md).

##  <a name="_core_the_csocket_programming_model"></a> CSocket programlama modeli

Kullanarak bir `CSocket` nesnesi oluşturma ve birlikte birkaç MFC sınıf nesnelerine ilişkilendirme ilgilidir. Genel aşağıdaki yordamda, her bir adımın sunucu yuvası ve her bir yuva türü farklı bir eylem gerektiren istemci yuvası, adım 3 ' dışında tarafından alınır.

> [!TIP]
>  Çalışma zamanında sunucu uygulaması genellikle önce hazır ve "istemci uygulama bir bağlantı çalışmaktadır, dinleme" başlar. İstemcinin bağlanmaya çalıştığında sunucunun hazır değilse, genellikle daha sonra yeniden bağlanmayı denemek için kullanıcı uygulaması gerektirir.

#### <a name="to-set-up-communication-between-a-server-socket-and-a-client-socket"></a>Bir sunucu yuvası ile bir istemci yuvası arasındaki iletişim kurmak için

1. Oluşturmak bir [CSocket](../mfc/reference/csocket-class.md) nesne.

1. Nesne arka plandaki oluşturmak için kullanın **YUVA** tanıtıcı.

     İçin bir `CSocket` istemci nesnesi, normalde kullanmanız gerektiğini varsayılan parametreleri [Oluştur](../mfc/reference/casyncsocket-class.md#create), bir veri birimi yuva gerekmedikçe. İçin bir `CSocket` sunucu nesnesi için bir bağlantı noktası belirtmeniz gerekir `Create` çağırın.

    > [!NOTE]
    >  `CArchive` veri birimi yuvaları ile çalışmaz. Kullanmak istiyorsanız `CSocket` bir veri birimi yuva için kullanacağınız gibi sınıf kullanmalısınız `CAsyncSocket`, diğer bir deyişle, bir arşiv olmadan. Veri birimlerini güvenilir olduğundan (ulşamasını garanti ve yinelenebilir değil veya sıra dışında), serileştirme yöntemiyle bir arşiv ile uyumlu değildir. Bir seri hale getirme işlemi, güvenilir ve sırayla tamamlanması beklediğiniz. Kullanmayı denerseniz `CSocket` ile bir `CArchive` nesne bir veri birimi için bir MFC onaylama işlemi başarısız olur.

1. Yuva bir istemciyse, çağrı [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect) yuva nesnesi için bir sunucu yuvası bağlanmak için.

     veya

     Yuva bir sunucuysa, çağrı [CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen) başlamak için bir istemciden bağlanma girişimleri noktasında dinler. Bir bağlantı isteği aldıktan sonra çağırarak kabul [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept).

    > [!NOTE]
    >  `Accept` Üye işlev yeni, boş bir başvuru alır `CSocket` parametre olarak nesne. Çağırmadan önce bu nesne oluşturmalıdır `Accept`. Bu yuva nesne kapsam dışına gider, bağlantıyı kapatır. Çağırmayın `Create` bu yeni bir yuva nesnesi.

1. Oluşturma bir [CSocketFile](../mfc/reference/csocketfile-class.md) nesne, ilişkilendirme `CSocket` olan nesne.

1. Oluşturma bir [CArchive](../mfc/reference/carchive-class.md) yükleme (alma) veya (gönderen) verileri depolamak için nesne. Arşiv ilişkili olduğu `CSocketFile` nesne.

     Aklınızda `CArchive` veri birimi yuvaları ile çalışmaz.

1. Kullanım `CArchive` istemci ve sunucu Yuvalar arasında veri iletmek için nesne.

     Aklınızda bir verilen `CArchive` nesneyi tek yönlü veri taşır: yükleme (alma) veya (gönderen) depolamak için. Bazı durumlarda, iki kullanacağınız `CArchive` nesneleri: bir bildirim almak için diğer veri göndermek için.

     Bir bağlantı kabul eden ve Arşiv ayarını sonra parolalar doğrulama gibi görevler gerçekleştirebilirsiniz.

1. Arşiv, yuva dosyasını ve yuva nesneler yok.

    > [!NOTE]
    >  Sınıf `CArchive` sağlayan `IsBufferEmpty` üye işlev sınıfı ile kullanılmak üzere özel olarak `CSocket`. Örneğin, arabellek birden çok veri iletileri içeriyorsa, bunların tümünün okuyun ve arabellek temizlenir kadar döngü gerekir. Aksi takdirde, süresiz olarak alınacak veri olduğunu, sonraki bildirim gecikebilir. Kullanım `IsBufferEmpty` tüm verileri almak güvence altına almak için.

Makaleyi [Windows Yuvaları: dizisi, işlemleri](../mfc/windows-sockets-sequence-of-operations.md) her iki tarafında bir örnek kod ile bu işlemi gösterilmektedir.

Daha fazla bilgi için bkz.:

- [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca Bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[CSocket::Create](../mfc/reference/csocket-class.md#create)

