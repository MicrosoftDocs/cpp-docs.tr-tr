---
title: 'Çoklu iş parçacığı kullanımı: MFC eşitleme sınıflarını kullanma'
ms.date: 08/27/2018
helpviewer_keywords:
- MFC [C++], multithreading
- threading [MFC], synchronization classes
- resources [C++], multithreading
- thread-safe classes [C++]
- synchronization classes [C++]
- synchronization [C++], multithreading
- threading [MFC], thread-safe class design
- threading [C++], synchronization
- multithreading [C++], synchronization classes
- threading [C++], thread-safe class design
ms.assetid: f266d4c6-0454-4bda-9758-26157ef74cc5
ms.openlocfilehash: 26a059e378edb92f5ff7f4e788ded90678e0c129
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511874"
---
# <a name="multithreading-how-to-use-the-mfc-synchronization-classes"></a>Çoklu iş parçacığı kullanımı: MFC eşitleme sınıflarını kullanma

İş parçacıkları arasında kaynak erişiminin eşitlenmesi, çok iş parçacıklı uygulamalar yazarken yaygın bir sorundur. Aynı verilere aynı anda iki veya daha fazla iş parçacığının bulunması istenmeyen ve öngörülemeyen sonuçlara yol açabilir. Örneğin, bir iş parçacığı başka bir iş parçacığı aynı yapının içeriğini okurken bir yapının içeriğini güncelleştiriyoruz. Okuma iş parçacığının alacağı veriler bilinmiyor: eski veriler, yeni yazılan veriler veya büyük olasılıkla her ikisinin karışımı. MFC, bu sorunu çözmeye yardımcı olacak bir dizi eşitleme ve eşitleme erişim sınıfı sağlar. Bu konu, kullanılabilen sınıfları ve tipik bir çok iş parçacıklı uygulamada iş parçacığı açısından güvenli sınıflar oluşturmak için nasıl kullanılacağını açıklamaktadır.

Tipik bir çok iş parçacıklı uygulamanın, iş parçacıkları arasında paylaşılacak bir kaynağı temsil eden sınıfı vardır. Düzgün tasarlanmış, tamamen iş parçacığı güvenli bir sınıf herhangi bir eşitleme işlevini çağırmanız gerekmez. Her şey sınıfında dahili olarak işlenir ve bu sınıfın nasıl bozulmuş olabileceği hakkında değil, sınıfının en iyi şekilde kullanılmasına odaklanmanızı sağlar. Tam iş parçacığı güvenli sınıfı oluşturmak için etkili bir teknik, eşitleme sınıfını kaynak sınıfına birleştirmektir. Eşitleme sınıflarını paylaşılan sınıfta birleştirme, basit bir işlemdir.

Örnek olarak, bağlı firmaların listesini tutan bir uygulama alın. Bu uygulama, ayrı Windows 'da en fazla üç hesap incelenmesine izin verir, ancak yalnızca bir tane belirli bir zamanda güncelleştirilebilen olabilir. Bir hesap güncelleştirildiği zaman, güncelleştirilmiş veriler ağ üzerinden bir veri arşivine gönderilir.

Bu örnek uygulama, üç tür eşitleme sınıfını kullanır. Tek seferde en fazla üç hesap incelendiğinden, üç görünüm nesnesine erişimi sınırlandırmak için [Csemafor](../mfc/reference/csemaphore-class.md) kullanır. Dördüncü bir hesabı görüntüleme denemesi gerçekleştiğinde, uygulama ilk üç Windows 'un kapanmasından veya başarısız olana kadar bekler. Bir hesap güncelleştirildiği zaman, uygulama, aynı anda yalnızca bir hesabın güncelleştirildiğinden emin olmak için [Ccriticalhandle bölümünü](../mfc/reference/ccriticalsection-class.md) kullanır. Güncelleştirme başarılı olduktan sonra, etkinlik için [](../mfc/reference/cevent-class.md)bekleyen bir iş parçacığını serbest bırakır. Bu iş parçacığı veri arşivine yeni verileri gönderir.

##  <a name="_mfc_designing_a_thread.2d.safe_class"></a>Iş parçacığı güvenli sınıfı tasarlama

Bir sınıfı tamamen iş parçacığı açısından güvenli hale getirmek için, önce uygun eşitleme sınıfını paylaşılan sınıflara bir veri üyesi olarak ekleyin. Önceki hesap yönetimi örneğinde, bir `CSemaphore` veri üyesi görünüm sınıfına eklenerek `CCriticalSection` , bağlantılı liste sınıfına bir veri üyesi eklenir ve veri depolama sınıfına bir `CEvent` veri üyesi eklenecektir.

Sonra, sınıftaki verileri değiştiren veya denetlenen kaynağa erişen tüm üye işlevlerine eşitleme çağrıları ekleyin. Her işlevde, bir [CSingleLock](../mfc/reference/csinglelock-class.md) veya [CMultiLock](../mfc/reference/cmultilock-class.md) nesnesi oluşturmalı ve `Lock` bu nesnenin işlevini çağırmanız gerekir. Kilit nesnesi kapsam dışına geçtiğinde ve yok edildiğinde, nesnenin yıkıcısı sizin için çağırır `Unlock` , kaynağı serbest bırakır. Kuşkusuz, isterseniz doğrudan çağırabilirsiniz `Unlock` .

İş parçacığı açısından güvenli sınıfınızı bu şekilde tasarlamak, iş parçacıklı bir uygulamada iş parçacığı güvenli olmayan bir sınıf olarak kolayca kullanılabilir, ancak daha yüksek bir güvenlik düzeyi sağlar. Eşitleme nesnesi ve eşitleme erişimi nesnesinin, kaynağın sınıfına kapsüllenmesi, eşitleme kodunu korumanın dezavantajı olmadan tamamen iş parçacığı açısından güvenli programlama avantajlarından yararlanır.

Aşağıdaki kod örneği, paylaşılan kaynak sınıfında ve bir `m_CritSection` `CSingleLock` nesnesinde belirtilen bir veri üyesini (türü `CCriticalSection`) kullanarak bu yöntemi gösterir. Paylaşılan kaynağın (türeten `CWinThread`türetilmiş) eşitlenmesi, `m_CritSection` nesnesinin adresi kullanılarak bir `CSingleLock` nesne oluşturularak denenir. Kaynağı kilitlemek için bir girişimde bulunuldu ve elde edildiğinde, paylaşılan nesne üzerinde iş yapılır. Çalışma bittiğinde, kaynak, öğesine `Unlock`yapılan çağrısıyla birlikte açılır.

```
CSingleLock singleLock(&m_CritSection);
singleLock.Lock();
// resource locked
//.usage of shared resource...

singleLock.Unlock();
```

> [!NOTE]
> `CCriticalSection`, diğer MFC eşitleme sınıflarının aksine, zamanlanmış bir kilit isteği seçeneğine sahip değildir. Bir iş parçacığının serbest olması için bekleme süresi sonsuz ' dur.

Bu yaklaşımın dezavantajları, sınıfın, eşitleme nesnelerinin eklenmeksizin aynı sınıftan biraz daha yavaş olabilmesidir. Ayrıca, birden fazla iş parçacığının nesneyi silebileceğinden, birleştirilmiş yaklaşımın her zaman çalışmama olasılığı vardır. Bu durumda, ayrı eşitleme nesnelerinin bakımını yapmak daha iyidir.

Farklı durumlarda hangi eşitleme sınıfının kullanılacağını belirleme hakkında daha fazla bilgi için bkz [. çoklu iş parçacığı: Eşitleme sınıfları](multithreading-when-to-use-the-synchronization-classes.md)ne zaman kullanılır? Eşitleme hakkında daha fazla bilgi için Windows SDK [eşitleme](/windows/win32/Sync/synchronization) bölümüne bakın. MFC 'de çoklu iş parçacıklı destek hakkında daha fazla bilgi için bkz. [Çoklu Iş parçacığı C++ ve MFC](multithreading-with-cpp-and-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)
