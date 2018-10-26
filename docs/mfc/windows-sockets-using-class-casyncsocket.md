---
title: "Windows Yuvaları: Sınıf Casyncsocket'ini kullanma | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CAsyncSocket
dev_langs:
- C++
helpviewer_keywords:
- CAsyncSocket class [MFC], programming model
- Windows Sockets [MFC], asynchronous
- sockets [MFC], converting between Unicode and MBCS strings
- SOCKET handle
- sockets [MFC], asynchronous operation
- Windows Sockets [MFC], converting Unicode and MBCS strings
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0aaefc41ca365e2bf4d87583f2e25dfa2a870a90
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079018"
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma

Bu makalede sınıfının nasıl kullanılacağını açıklayan [Casyncsocket'ini](../mfc/reference/casyncsocket-class.md). Bu sınıf Windows Sockets API'SİNİN çok düşük bir düzeyde kapsülleyen dikkat edin. `CAsyncSocket` ayrıntılı ağ iletişimleri biliyorsanız ancak ağ olay bildirimi için geri çağırmaları kolaylık istediğiniz programcılara tarafından kullanılır. Bu makalede, bu varsayımına dayanarak, yalnızca temel yönergeler sağlar. Büyük olasılıkla kullanmayı düşünmelisiniz `CAsyncSocket` Windows Sockets MFC uygulamasında birden fazla ağ protokolleri uğraşmanızı kolaylığı istiyor, ancak esneklik özelliğinden faydalanmasına istemediğiniz. Daha fazla iletişim kendiniz daha kullanarak doğrudan daha genel alternatif model sınıfı programlayarak daha iyi verimlilik elde edebilirsiniz ayrıca ilerlediğini düşünebilirsiniz `CSocket`.

`CAsyncSocket` belgelenen *MFC başvurusu*. Visual C++, ayrıca Windows SDK'da bulunan Windows yuva belirtimi sağlar. Ayrıntılar için bırakılır. Visual C++ için örnek bir uygulama sağlamazsa `CAsyncSocket`.

Ağ iletişimi hakkında yüksek düzeyde bilgili değildir ve basit bir çözüm'i istiyorsanız sınıfını kullanmak [CSocket](../mfc/reference/csocket-class.md) ile bir `CArchive` nesne. Bkz: [Windows Yuvaları: yuvaların arşivlerle kullanma](../mfc/windows-sockets-using-sockets-with-archives.md) daha fazla bilgi için.

Bu makalede ele alınmıştır:

- Oluşturma ve kullanma bir `CAsyncSocket` nesne.

- [Sizin Sorumluluklarınız ile Casyncsocket'ini](#_core_your_responsibilities_with_casyncsocket).

##  <a name="_core_creating_and_using_a_casyncsocket_object"></a> Oluşturma ve bir Casyncsocket'ini nesnesi kullanma

#### <a name="to-use-casyncsocket"></a>CAsyncSocket kullanmak için

1. Oluşturmak bir [Casyncsocket'ini](../mfc/reference/casyncsocket-class.md) nesnesini ve nesne temel alınan oluşturun **YUVA** tanıtıcı.

   Bir yuva oluşturulmasını iki aşamalı yapımı MFC desenini izler.

   Örneğin:

   [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]

     veya

   [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]

   Yukarıdaki ilk Oluşturucu bir `CAsyncSocket` yığında nesne. İkinci oluşturucu bir `CAsyncSocket` yığında. İlk [Oluştur](../mfc/reference/casyncsocket-class.md#create) yukarıdaki çağrı stream yuva oluşturma için varsayılan parametreleri kullanır. İkinci `Create` çağrı, belirtilen bağlantı noktası ve adresi ile bir veri birimi yuva oluşturur. (Kullanabilirsiniz `Create` ya da oluşturma yöntemiyle sürümü.)

   Parametreleri `Create` şunlardır:

   - "Bağlantı noktası": kısa bir tamsayı.

         For a server socket, you must specify a port. For a client socket, you typically accept the default value for this parameter, which lets Windows Sockets select a port.

   - Bir yuva türü: **SOCK_STREAM** (varsayılan) veya **SOCK_DGRAM**.

   - Bir yuva "," gibi adresi "ftp.microsoft.com" veya "128.56.22.8".

         This is your Internet Protocol (IP) address on the network. You will probably always rely on the default value for this parameter.

   Koşulları "bağlantı noktası" ve "yuva adresi" açıklanmıştır [Windows Yuvaları: bağlantı noktaları ve yuva adresleri](../mfc/windows-sockets-ports-and-socket-addresses.md).

1. Yuva bir istemciyse, yuva nesnesi cuya Bağlan kullanarak yuva [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect).

     veya

   Yuva sunucusuysa dinleme başlamak için yuva ayarlayın (ile [CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen)) için bir istemciden bağlanma girişimleri. Bir bağlantı isteği aldıktan sonra onunla kabul [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept).

   Bir bağlantı kabul ettikten sonra parolalar doğrulama gibi görevler gerçekleştirebilirsiniz.

    > [!NOTE]
    >  `Accept` Üye işlev yeni, boş bir başvuru alır `CSocket` parametre olarak nesne. Çağırmadan önce bu nesne oluşturmalıdır `Accept`. Bu yuva nesne kapsam dışına gider, bağlantıyı kapatır. Çağırmayın `Create` bu yeni bir yuva nesnesi. Bir örnek için bkz [Windows Yuvaları: dizisi, işlemleri](../mfc/windows-sockets-sequence-of-operations.md).

1. Çağırarak diğer yuva iletişimi yürütmek `CAsyncSocket` Windows Sockets API'SİNİN işlevleri kapsülleyen bir nesnenin üye işlevleri.

   Bkz: Windows yuva belirtimi ve sınıf [Casyncsocket'ini](../mfc/reference/casyncsocket-class.md) içinde *MFC başvurusu*.

1. Destroy `CAsyncSocket` nesne.

   Yuva nesneyi yığında oluşturduysanız, yok edici içeren işlev kapsam dışına çıktığında çağırılır. Yuva nesneyi yığında oluşturduysanız, kullanarak **yeni** işleci, işiniz kullanmak için sorumlu **Sil** nesneyi yok etmek için işleci.

   Nesnenin yok edici çağrıları [Kapat](../mfc/reference/casyncsocket-class.md#close) nesneyi yok etmek önce üye işlevi.

Bu sırada bir kod örneği için (için gerçekten bir `CSocket` nesne), bkz [Windows Yuvaları: dizisi, işlemleri](../mfc/windows-sockets-sequence-of-operations.md).

##  <a name="_core_your_responsibilities_with_casyncsocket"></a> CAsyncSocket ile sizin Sorumluluklarınız

Sınıfın bir nesnesi oluşturduğunuzda [Casyncsocket'ini](../mfc/reference/casyncsocket-class.md), nesnenin bir Windows Kapsüller **YUVA** işlemek ve o tanıtıcının işlemleri sağlar. Kullanırken `CAsyncSocket`, yüz API doğrudan kullanıyorsanız tüm sorunları ile işlem yapması gerekir. Örneğin:

- "Engelleme" senaryoları.

- Bayt sırası farklar gönderip makineler arasında.

- Unicode ve çok baytlı karakter arasında dönüştürme (MBCS) dizeleri ayarlayın.

Bu hüküm ve ek bilgiler tanımları için bkz. [Windows Yuvaları: engelleme](../mfc/windows-sockets-blocking.md), [Windows Yuvaları: bayt sıralama](../mfc/windows-sockets-byte-ordering.md), [Windows Yuvaları: dizeleri dönüştürme](../mfc/windows-sockets-converting-strings.md) .

Bu sorunları rağmen sınıf `CAsycnSocket` uygulamanıza esneklik ve denetim elde edebilirsiniz gerekiyorsa doğru seçim sizin için uygun olabilir. Sınıf kullanmayı düşünmeniz gerekir, varsa `CSocket` yerine. `CSocket` çok fazla ayrıntı sizden gizler: Windows iletilerini çağrıları engelleyici sırasında ve size pompalara erişmek için BT `CArchive`, bayt sırası farkları ve sizin için dize dönüştürme yönetir.

Daha fazla bilgi için bkz.:

- [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

- [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca Bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)

