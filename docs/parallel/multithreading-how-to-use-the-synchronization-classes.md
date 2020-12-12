---
description: 'Daha fazla bilgi edinin: çoklu Iş parçacığı kullanımı: MFC eşitleme sınıflarını kullanma'
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
ms.openlocfilehash: a62bdba992ef8b65c14991da26e098f545c30ccd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149922"
---
# <a name="multithreading-how-to-use-the-mfc-synchronization-classes"></a>Çoklu iş parçacığı kullanımı: MFC eşitleme sınıflarını kullanma

İş parçacıkları arasında kaynak erişiminin eşitlenmesi, çok iş parçacıklı uygulamalar yazarken yaygın bir sorundur. Aynı verilere aynı anda iki veya daha fazla iş parçacığının bulunması istenmeyen ve öngörülemeyen sonuçlara yol açabilir. Örneğin, bir iş parçacığı başka bir iş parçacığı aynı yapının içeriğini okurken bir yapının içeriğini güncelleştiriyoruz. Okuma iş parçacığının alacağı veriler bilinmiyor: eski veriler, yeni yazılan veriler veya büyük olasılıkla her ikisinin karışımı. MFC, bu sorunu çözmeye yardımcı olacak bir dizi eşitleme ve eşitleme erişim sınıfı sağlar. Bu konu, kullanılabilen sınıfları ve tipik bir çok iş parçacıklı uygulamada iş parçacığı açısından güvenli sınıflar oluşturmak için nasıl kullanılacağını açıklamaktadır.

Tipik bir çok iş parçacıklı uygulamanın, iş parçacıkları arasında paylaşılacak bir kaynağı temsil eden sınıfı vardır. Düzgün tasarlanmış, tamamen iş parçacığı güvenli bir sınıf herhangi bir eşitleme işlevini çağırmanız gerekmez. Her şey sınıfında dahili olarak işlenir ve bu sınıfın nasıl bozulmuş olabileceği hakkında değil, sınıfının en iyi şekilde kullanılmasına odaklanmanızı sağlar. Tam iş parçacığı güvenli sınıfı oluşturmak için etkili bir teknik, eşitleme sınıfını kaynak sınıfına birleştirmektir. Eşitleme sınıflarını paylaşılan sınıfta birleştirme, basit bir işlemdir.

Örnek olarak, bağlı firmaların listesini tutan bir uygulama alın. Bu uygulama, ayrı Windows 'da en fazla üç hesap incelenmesine izin verir, ancak yalnızca bir tane belirli bir zamanda güncelleştirilebilen olabilir. Bir hesap güncelleştirildiği zaman, güncelleştirilmiş veriler ağ üzerinden bir veri arşivine gönderilir.

Bu örnek uygulama, üç tür eşitleme sınıfını kullanır. Tek seferde en fazla üç hesap incelendiğinden, üç görünüm nesnesine erişimi sınırlandırmak için [Csemafor](../mfc/reference/csemaphore-class.md) kullanır. Dördüncü bir hesabı görüntüleme denemesi gerçekleştiğinde, uygulama ilk üç Windows 'un kapanmasından veya başarısız olana kadar bekler. Bir hesap güncelleştirildiği zaman, uygulama, aynı anda yalnızca bir hesabın güncelleştirildiğinden emin olmak için [Ccriticalhandle bölümünü](../mfc/reference/ccriticalsection-class.md) kullanır. Güncelleştirme başarılı olduktan [sonra, etkinlik](../mfc/reference/cevent-class.md)için bekleyen bir iş parçacığını serbest bırakır. Bu iş parçacığı veri arşivine yeni verileri gönderir.

## <a name="designing-a-thread-safe-class"></a><a name="_mfc_designing_a_thread.2d.safe_class"></a> Thread-Safe sınıfı tasarlama

Bir sınıfı tamamen iş parçacığı açısından güvenli hale getirmek için, önce uygun eşitleme sınıfını paylaşılan sınıflara bir veri üyesi olarak ekleyin. Önceki hesap yönetimi örneğinde, bir `CSemaphore` veri üyesi görünüm sınıfına eklenerek, bağlantılı liste sınıfına bir veri üyesi eklenir `CCriticalSection` ve veri `CEvent` depolama sınıfına bir veri üyesi eklenecektir.

Sonra, sınıftaki verileri değiştiren veya denetlenen kaynağa erişen tüm üye işlevlerine eşitleme çağrıları ekleyin. Her işlevde, bir [CSingleLock](../mfc/reference/csinglelock-class.md) veya [CMultiLock](../mfc/reference/cmultilock-class.md) nesnesi oluşturmalı ve bu nesnenin işlevini çağırmanız gerekir `Lock` . Kilit nesnesi kapsam dışına geçtiğinde ve yok edildiğinde, nesnenin yıkıcısı `Unlock` sizin için çağırır, kaynağı serbest bırakır. Kuşkusuz, `Unlock` isterseniz doğrudan çağırabilirsiniz.

İş parçacığı açısından güvenli sınıfınızı bu şekilde tasarlamak, iş parçacıklı bir uygulamada iş parçacığı güvenli olmayan bir sınıf olarak kolayca kullanılabilir, ancak daha yüksek bir güvenlik düzeyi sağlar. Eşitleme nesnesi ve eşitleme erişimi nesnesinin, kaynağın sınıfına kapsüllenmesi, eşitleme kodunu korumanın dezavantajı olmadan tamamen iş parçacığı açısından güvenli programlama avantajlarından yararlanır.

Aşağıdaki kod örneği, `m_CritSection` `CCriticalSection` paylaşılan kaynak sınıfında ve bir nesnesinde belirtilen bir veri üyesini (türü) kullanarak bu yöntemi gösterir `CSingleLock` . Paylaşılan kaynağın (türeten türetilmiş) eşitlenmesi, `CWinThread` `CSingleLock` nesnesinin adresi kullanılarak bir nesne oluşturularak denenir `m_CritSection` . Kaynağı kilitlemek için bir girişimde bulunuldu ve elde edildiğinde, paylaşılan nesne üzerinde iş yapılır. Çalışma bittiğinde, kaynak, öğesine yapılan çağrısıyla birlikte açılır `Unlock` .

```cpp
CSingleLock singleLock(&m_CritSection);
singleLock.Lock();
// resource locked
//.usage of shared resource...

singleLock.Unlock();
```

> [!NOTE]
> `CCriticalSection`, diğer MFC eşitleme sınıflarının aksine, zamanlanmış bir kilit isteği seçeneğine sahip değildir. Bir iş parçacığının serbest olması için bekleme süresi sonsuz ' dur.

Bu yaklaşımın dezavantajları, sınıfın, eşitleme nesnelerinin eklenmeksizin aynı sınıftan biraz daha yavaş olabilmesidir. Ayrıca, birden fazla iş parçacığının nesneyi silebileceğinden, birleştirilmiş yaklaşımın her zaman çalışmama olasılığı vardır. Bu durumda, ayrı eşitleme nesnelerinin bakımını yapmak daha iyidir.

Farklı durumlarda kullanılacak eşitleme sınıfını belirleme hakkında daha fazla bilgi için bkz. [Çoklu Iş parçacığı kullanımı: eşitleme sınıfları ne zaman kullanılır](multithreading-when-to-use-the-synchronization-classes.md)?. Eşitleme hakkında daha fazla bilgi için Windows SDK [eşitleme](/windows/win32/Sync/synchronization) bölümüne bakın. MFC 'de çoklu iş parçacıklı destek hakkında daha fazla bilgi için bkz. [Çoklu Iş parçacığı C++ ve MFC](multithreading-with-cpp-and-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)
