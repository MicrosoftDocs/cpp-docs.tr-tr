---
title: "Windows Yuvaları: Sınıf Casyncsocket'ini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CAsyncSocket
dev_langs: C++
helpviewer_keywords:
- CAsyncSocket class [MFC], programming model
- Windows Sockets [MFC], asynchronous
- sockets [MFC], converting between Unicode and MBCS strings
- SOCKET handle
- sockets [MFC], asynchronous operation
- Windows Sockets [MFC], converting Unicode and MBCS strings
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 41a1bf9e7b162ecfe9724f22996f8883d95cce72
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma
Bu makalede sınıfının nasıl kullanılacağını açıklanmaktadır [CAsyncSocket](../mfc/reference/casyncsocket-class.md). Bu sınıf Windows Sockets API çok düşük düzeyde yalıtır unutmayın. `CAsyncSocket`ayrıntılı ağ iletişimleri bilmeniz ancak ağ olayları bildirim için geri çağırmaları kolaylık istediğiniz programcıları tarafından kullanılır. Bu makalede, bu duymadığını, yalnızca temel yönergeler sağlar. Büyük olasılıkla kullanmayı düşünmelisiniz `CAsyncSocket` bir MFC uygulamasında birden çok ağ protokolleri postalarla Windows Sockets kolaylığı istiyor, ancak esneklik yöneticilerin taviz istiyor musunuz. Daha fazla iletişim kendiniz daha kullanarak doğrudan daha genel alternatif modeli sınıfının programlama tarafından daha iyi verimlilik elde edebilirsiniz ayrıca eşitleyerek `CSocket`.  
  
 `CAsyncSocket`belgelenen *MFC başvurusu*. Visual C++ Windows SDK'da bulunan Windows Sockets belirtimi de sağlar. Ayrıntılar için bırakılır. Visual C++ örnek bir uygulama için sağlamıyorsa `CAsyncSocket`.  
  
 Yüksek oranda ağ iletişimleri hakkında bilgi sahibi değildir ve basit bir çözüm istiyorsanız sınıfını kullanmak [CSocket](../mfc/reference/csocket-class.md) ile bir `CArchive` nesnesi. Bkz: [Windows Yuvaları: arşivlerle kullanılan yuvalara](../mfc/windows-sockets-using-sockets-with-archives.md) daha fazla bilgi için.  
  
 Bu makalede yer almaktadır:  
  
-   Oluşturma ve kullanma bir `CAsyncSocket` nesnesi.  
  
-   [Sizin Sorumluluklarınız CAsyncSocket ile](#_core_your_responsibilities_with_casyncsocket).  
  
##  <a name="_core_creating_and_using_a_casyncsocket_object"></a>Oluşturma ve bir CAsyncSocket nesnesi kullanma  
  
#### <a name="to-use-casyncsocket"></a>CAsyncSocket kullanmak için  
  
1.  Oluşturmak bir [CAsyncSocket](../mfc/reference/casyncsocket-class.md) nesne ve arka plandaki oluşturmak için nesne **YUVA** tanıtıcı.  
  
     Bir yuva oluşturulmasını iki aşamalı yapımı MFC desenini izler.  
  
     Örneğin:  
  
     [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]  
  
     veya  
  
     [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]  
  
     Yukarıdaki ilk Oluşturucusu oluşturur bir `CAsyncSocket` yığında nesnesi. İkinci oluşturucu oluşturur bir `CAsyncSocket` yığında. İlk [oluşturma](../mfc/reference/casyncsocket-class.md#create) çağrısı yukarıdaki bir akışa yuva oluşturmak için varsayılan parametreleri kullanır. İkinci **oluşturma** çağrısı, belirtilen bağlantı noktası ve adresi ile bir veri birimi yuva oluşturur. (Kullanabilirsiniz **oluşturma** yapım yöntemlerden sürümüyle.)  
  
     Parametreleri **oluşturma** şunlardır:  
  
    -   "Bağlantı noktası": kısa bir tamsayıdır.  
  
         Bir sunucu yuva için bir bağlantı noktası belirtmeniz gerekir. İstemci yuvası için genellikle Windows Sockets bir bağlantı noktası seçme olanağı sağlayan bu parametre için varsayılan değer kabul etmiş olursunuz.  
  
    -   Bir yuva türü: **SOCK_STREAM** (varsayılan) veya **SOCK_DGRAM**.  
  
    -   Bir yuva "," gibi adresi "ftp.microsoft.com" veya "128.56.22.8".  
  
         Ağ üzerinde Internet Protokolü (IP) adresi budur. Bu parametre için varsayılan değer büyük olasılıkla her zaman bağlı.  
  
     Koşulları "port" ve "yuva adresi" açıklanacak [Windows Yuvaları: bağlantı noktaları ve yuva adresleri](../mfc/windows-sockets-ports-and-socket-addresses.md).  
  
2.  Yuva bir istemci ise, yuva nesnesi bir sunucuya yuva, kullanarak [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect).  
  
     veya  
  
     Yuva bir sunucu ise dinleme yapmaya başlamasını yuva ayarlayın (ile [CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen)) bir istemciden bağlanma girişimleri için. Bir bağlantı isteği alındıktan sonra kendisiyle kabul [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept).  
  
     Bir bağlantı kabul ettikten sonra parolalar doğrulama gibi görevleri gerçekleştirebilirsiniz.  
  
    > [!NOTE]
    >  **Kabul** üye işlevi yeni, boş bir başvuru alır `CSocket` , parametre olarak nesne. Arama yapmadan önce bu nesneyi oluşturmalıdır **kabul**. Bu yuva nesne kapsam dışında kalırsa, bağlantıyı kapatır. Çağırmayın **oluşturma** bu yeni yuva nesnesi için. Bir örnek için bkz: [Windows Yuvaları: sırası, işlemleri](../mfc/windows-sockets-sequence-of-operations.md).  
  
3.  Çağırarak diğer yuva iletişimleri gerçekleştiremeyen `CAsyncSocket` Windows Sockets API işlevleri kapsülleyen nesnenin üye işlevleri.  
  
     Windows Yuvaları belirtimi ve sınıf bkz [CAsyncSocket](../mfc/reference/casyncsocket-class.md) içinde *MFC başvurusu*.  
  
4.  Destroy `CAsyncSocket` nesnesi.  
  
     Yığında yuva nesnesi oluşturduysanız, içeren işlevi kapsam dışına çıktığında, yıkıcı adı verilir. Öbek üzerinde yuva nesnesi oluşturduysanız, kullanarak **yeni** işleci, kullanmak için sorumlu **silmek** işleci nesne yok.  
  
     Nesnenin yıkıcı çağrıları [Kapat](../mfc/reference/casyncsocket-class.md#close) nesne yok etme önce üye işlevi.  
  
 Bu sırayla kod örneği için (gerçekte için bir `CSocket` nesne), bkz: [Windows Yuvaları: sırası, işlemleri](../mfc/windows-sockets-sequence-of-operations.md).  
  
##  <a name="_core_your_responsibilities_with_casyncsocket"></a>CAsyncSocket ile sizin Sorumluluklarınız  
 Sınıfın bir nesnesi oluştururken [CAsyncSocket](../mfc/reference/casyncsocket-class.md), Windows nesneyi yalıtır **YUVA** işlemek ve o tanıtıcının işlemler sağlar. Kullandığınızda `CAsyncSocket`, yüz API doğrudan kullanıyorsanız, tüm sorunlarla ilgilidir. Örneğin:  
  
-   "Engelleme" senaryoları.  
  
-   Bayt sırası farklarını gönderip makineler.  
  
-   Birden çok baytlı karakter ve Unicode arasında dönüştürme (MBCS) dizeleri ayarlayın.  
  
 Bu hüküm ve ek bilgiler tanımları için bkz: [Windows Yuvaları: engelleme](../mfc/windows-sockets-blocking.md), [Windows Yuvaları: bayt sıralama](../mfc/windows-sockets-byte-ordering.md), [Windows Yuvaları: dizeleri dönüştürme](../mfc/windows-sockets-converting-strings.md) .  
  
 Bu sorunların rağmen sınıf **CAsycnSocket** tüm alabilirsiniz denetim ve esneklik uygulamanızı gerektiriyorsa, doğru seçim sizin için olabilir. Sınıf kullanmayı düşünmeniz gerekir, varsa `CSocket` yerine. `CSocket`çok fazla ayrıntı sizden gizler: Windows iletilerini çağrıları engelleme sırasında ve verir Pompalar erişmek için BT `CArchive`, bayt sırası farklar ve sizin için dize dönüştürme yönetir.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)  
  
-   [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)

