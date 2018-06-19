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
ms.openlocfilehash: b7ad4e5b94403582f9073e4d3bd3542f8aa75d08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385544"
---
# <a name="windows-sockets-using-sockets-with-archives"></a>Windows Yuvaları: Yuvaları Arşivlerle Kullanma
Bu makalede [CSocket programlama modeli](#_core_the_csocket_programming_model). Sınıf [CSocket](../mfc/reference/csocket-class.md) sınıfı daha soyutlama daha yüksek düzeyde yuva desteği sağlayan [CAsyncSocket](../mfc/reference/casyncsocket-class.md). `CSocket` bir yuva nesnesi bir MFC üzerinden veri iletmek için MFC serileştirme protokolü bir sürümünü kullanan [CArchive](../mfc/reference/carchive-class.md) nesnesi. `CSocket` (Windows iletilerinin arka plan işleme yönetirken) engelleme sağlar ve için erişmenizi `CArchive`, pek çok görünüşünün ham API veya sınıfı kullanarak kendiniz yapmak zorunda iletişimi yöneten `CAsyncSocket`.  
  
> [!TIP]
>  Sınıf kullanabilirsiniz `CSocket` daha kullanışlı bir sürümü olarak kendisi tarafından `CAsyncSocket`, ancak basit programlama modeli kullanmaktır `CSocket` ile bir `CArchive` nesnesi.  
  
 Yuvaların arşivlerle uyarlamasını nasıl çalıştığı hakkında daha fazla bilgi için bkz: [Windows Yuvaları: Yuva arşivler iş nasıl](../mfc/windows-sockets-how-sockets-with-archives-work.md). Örnek kod, bkz: [Windows Yuvaları: sırası, işlemleri](../mfc/windows-sockets-sequence-of-operations.md) ve [Windows Yuvaları: örnek, yuva kullanarak arşivler](../mfc/windows-sockets-example-of-sockets-using-archives.md). Elde kendi sınıflarınızı yuva sınıflarından türetme tarafından bazı işlevleri hakkında bilgi için bkz [Windows Yuvaları: Yuva sınıflarından türetme](../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
> [!NOTE]
>  Kurulan (MFC olmayan) sunucularıyla iletişim kurmak için bir MFC istemci programı yazıyorsanız, arşiv C++ nesnelerde göndermeyin. Sunucu göndermek istediğiniz nesne türlerini özelliğini algılayan bir MFC uygulaması olmadığı sürece almak ve nesnelerinizin seri durumdan mümkün olmaz. MFC dışı uygulamalar ile iletişim konuyla ilgili malzemeleri için makale ayrıca bkz. [Windows Yuvaları: bayt sıralama](../mfc/windows-sockets-byte-ordering.md).  
  
##  <a name="_core_the_csocket_programming_model"></a> CSocket programlama modeli  
 Kullanarak bir `CSocket` nesnesi oluşturma ve birlikte birkaç MFC sınıf nesnelerine ilişkilendirme ilgilidir. Genel aşağıdaki yordamda, her adım server yuva ve her yuva türü farklı bir eylem gerektiren istemci yuvası, adım 3 ' ü dışında tarafından alınır.  
  
> [!TIP]
>  Çalışma zamanında sunucu uygulaması genellikle ilk hazır ve "istemci uygulaması bağlantı aradığı zaman dinleme" olarak başlatır. İstemcinin bağlanmaya çalıştığında, sunucunun hazır değilse, genellikle daha sonra yeniden bağlanmayı denemek için kullanıcı uygulaması gerektirir.  
  
#### <a name="to-set-up-communication-between-a-server-socket-and-a-client-socket"></a>Bir sunucu yuva istemci yuvası arasındaki iletişimi ayarlamak için  
  
1.  Oluşturmak bir [CSocket](../mfc/reference/csocket-class.md) nesnesi.  
  
2.  Arka plandaki oluşturmak için nesne kullanın **YUVA** işler.  
  
     İçin bir `CSocket` istemci nesnesi, normalde kullanmanız gereken varsayılan parametreleri [oluşturma](../mfc/reference/casyncsocket-class.md#create), veri birimi yuva gerekmedikçe. İçin bir `CSocket` sunucusu nesnesi, bir bağlantı noktası belirtmeniz gerekir **oluşturma** çağırın.  
  
    > [!NOTE]
    >  `CArchive` veri birimi yuvaları ile çalışmaz. Kullanmak istiyorsanız, `CSocket` bir veri birimi yuva için kullanacağınız gibi sınıfı kullanmalısınız `CAsyncSocket`, diğer bir deyişle, bir arşiv olmadan. Veri birimleri güvenilir olduğundan (gelmesi garanti ve yinelenebilir veya sırası dışında), serileştirme bir arşiv üzerinden ile uyumlu değildir. Güvenilir ve sırasını tamamlamak için bir seri hale getirme işlemi bekler. Kullanmayı denerseniz `CSocket` ile bir `CArchive` nesne bir veri birimi için bir MFC onaylama işlemi başarısız olur.  
  
3.  Yuva istemci çağırır [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect) yuva nesnesi için bir sunucu yuvasına bağlanma.  
  
     -veya-  
  
     Yuva bir sunucu ise, çağrı [CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen) başlamak için bir istemciden bağlantısı girişimi için dinler. Bir bağlantı isteği alındıktan sonra çağırarak kabul [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept).  
  
    > [!NOTE]
    >  **Kabul** üye işlevi yeni, boş bir başvuru alır `CSocket` , parametre olarak nesne. Arama yapmadan önce bu nesneyi oluşturmalıdır **kabul**. Bu yuva nesne kapsam dışında kalırsa, bağlantıyı kapatır. Çağırmayın **oluşturma** bu yeni yuva nesnesi için.  
  
4.  Oluşturma bir [CSocketFile](../mfc/reference/csocketfile-class.md) nesnesi, ilişkilendirme `CSocket` onunla nesnesi.  
  
5.  Oluşturma bir [CArchive](../mfc/reference/carchive-class.md) yükleme (alma) veya (gönderen) verileri depolamak için nesne. Arşiv ilişkili olduğu `CSocketFile` nesnesi.  
  
     Aklınızda `CArchive` veri birimi yuvaları ile çalışmaz.  
  
6.  Kullanım `CArchive` istemci ve sunucu yuvaları arasında veri iletmek için nesne.  
  
     Aklınızda bir verilen `CArchive` nesne tek yönlü verileri taşır: yükleme (alma) veya (gönderen) depolamak için. Bazı durumlarda, iki kullanacağınız `CArchive` nesneleri: bir bildirim almak için diğer veri göndermek için.  
  
     Bir bağlantı kabul etmek ve Arşiv ayarını sonra parolalar doğrulama gibi görevleri gerçekleştirebilir.  
  
7.  Arşiv, yuva dosya ve yuva nesneler yok.  
  
    > [!NOTE]
    >  Sınıf `CArchive` sağlayan `IsBufferEmpty` üye işlevi sınıfı ile kullanılmak üzere özel olarak `CSocket`. Örneğin, birden fazla veri ileti arabellek içeriyorsa, bunların tümünün salt okunurdur ve arabellek temizlenir kadar döngü gerekir. Aksi halde, sonraki bildiriminizin alınacak veri olduğunu süresiz olarak gecikebilir. Kullanım `IsBufferEmpty` tüm verileri almak güvence altına almak için.  
  
 Makaleyi [Windows Yuvaları: sırası, işlemleri](../mfc/windows-sockets-sequence-of-operations.md) iki tarafı da bu işlem örnek kodu gösterir.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)   
 [CSocket::Create](../mfc/reference/csocket-class.md#create)

