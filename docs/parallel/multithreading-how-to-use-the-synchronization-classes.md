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
ms.openlocfilehash: 6115d942abc61fbfc9d60ca1ccf97d4b423ff7c1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407698"
---
# <a name="multithreading-how-to-use-the-mfc-synchronization-classes"></a>Çoklu iş parçacığı kullanımı: MFC eşitleme sınıflarını kullanma

İş parçacıkları arasında kaynak erişim eşitleme yaygın çok iş parçacıklı uygulamalarda yazılırken bir sorundur. İki veya daha fazla sorun aynı anda aynı verilere istenmeyen ve beklenmeyen sonuçlara yol açabilir, erişim iş parçacıkları. Örneğin, başka bir iş parçacığı aynı yapıya içeriğini okuyor sırasında bir iş parçacığı bir yapının içeriği güncelleştirme. Hangi verileri okuma iş parçacığında alacağı bilinmiyor: eski verileri, yeni yazılmış veri veya büyük olasılıkla ikisinin karışımı olamaz. MFC, çok sayıda eşitleme ve bu sorunun çözümüne yardımcı olmak için eşitleme erişim sınıfları sağlar. Bu konu, kullanılabilir sınıflar ve bunları tipik bir çok iş parçacıklı uygulamada iş parçacığı açısından güvenli sınıflar oluşturmak için nasıl kullanılacağını açıklar.

Tipik bir çok iş parçacıklı uygulamanın iş parçacıkları arasında paylaşılan bir kaynağı temsil eden bir sınıfı vardır. Düzgün bir şekilde tasarlanmış, tamamen iş parçacığı açısından güvenli sınıf herhangi bir eşitleme işlevi çağırmak gerektirmez. Her şey en iyi şekilde kullanmanız konusunda nasıl, bozulmuş değil hakkında sınıfı odaklanmasına olanak sağlayan bir sınıf için dahili olarak işlenir. Bir tam iş parçacığı açısından güvenli sınıf oluşturmak için bir etkili teknik kaynak sınıfına eşitleme sınıfını birleştirilmesidir. Eşitleme sınıfları paylaşılan sınıfına birleştirme, basit bir işlemdir.

Örneğin, bağlantılı hesaplar listesini tutar uygulamanın yararlanın. Bu uygulamanın ayrı windows incelenmesi için en fazla üç hesapları sağlar, ancak belirli bir zamanda yalnızca biri güncelleştirilebilir. Bir hesap güncelleştirildiğinde güncelleştirilen verileri bir veri arşivine ağ üzerinden gönderilir.

Bu örnek uygulama, üç tür eşitleme sınıfları kullanır. Aynı anda incelenecek en fazla üç hesapları izin verdiğinden, kullandığı [CSemaphore](../mfc/reference/csemaphore-class.md) üç görünüm nesnelerine erişimi sınırlamak için. Görüntüleme girişiminde dördüncü bir hesabı meydana gelir, ilk üç windows birini kapatır veya başarısız kadar bekler ya da uygulama. Bir hesap güncelleştirildiğinde uygulamanın kullandığı [CCriticalSection](../mfc/reference/ccriticalsection-class.md) aynı anda yalnızca bir hesap güncelleştirildiğinden emin olmak için. Güncelleştirme başarılı olduktan sonra bildirir [CEvent](../mfc/reference/cevent-class.md), sinyal olayı için bekleyen bir iş parçacığını serbest bırakır. Bu iş parçacığı veri arşivine yeni verileri gönderir.

##  <a name="_mfc_designing_a_thread.2d.safe_class"></a> Bir iş parçacığı açısından güvenli sınıf tasarımı

Bir sınıf tam iş parçacığı açısından güvenli hale getirmek için önce uygun eşitleme sınıfını paylaşılan sınıfları veri üyesi olarak ekleyin. Önceki örnekte hesap yönetimi, bir `CSemaphore` veri üyesi görünüm sınıfına eklenen bir `CCriticalSection` veri üyesi bağlantılı liste sınıfa eklenmesi ve bir `CEvent` veri üyesi veri depolama sınıfına eklenmesi.

Ardından, eşitleme çağrıları sınıf verileri değiştiren veya denetimli kaynak erişimi tüm üye işlevleri ekleyin. Her işlevde, ya da oluşturmalısınız bir [CSingleLock](../mfc/reference/csinglelock-class.md) veya [CMultiLock](../mfc/reference/cmultilock-class.md) nesne ve o nesnenin `Lock` işlevi. Kilit nesne kapsam dışına gider ve edildiğinde, nesnenin yok Edicisi çağırır `Unlock` , kaynak serbest bırakma. Elbette, çağırabilirsiniz `Unlock` doğrudan istiyorsanız.

Bu şekilde, iş parçacığı açısından güvenli sınıf tasarımı birden çok iş parçacıklı uygulamada bir iş parçacığı güvenli olmayan sınıf olarak kolayca, ancak daha yüksek düzeyde güvenlik kullanılmasını sağlar. Eşitleme nesnesi ve eşitleme erişimi nesnesi kaynak sınıfına Kapsüllenen eşitleme kodu bakım dezavantajı tam iş parçacığı açısından güvenli programlamadan tüm avantajlarını sağlar.

Bir veri üyesi kullanarak bu yöntem aşağıdaki kod örneği gösterilmektedir `m_CritSection` (türü `CCriticalSection`), paylaşılan bir kaynak sınıfı olarak bildirilmiş ve bir `CSingleLock` nesne. Paylaşılan kaynak eşitlenmesi (türetilen `CWinThread`) oluşturarak denenir bir `CSingleLock` nesnesinin adresini kullanarak `m_CritSection` nesne. Kaynak kilidi için bir girişimde ve elde edilen zaman işler paylaşılan nesne üzerinde gerçekleştirilir. İş tamamlandığında, kaynak çağrısı ile açılmış `Unlock`.

```
CSingleLock singleLock(&m_CritSection);
singleLock.Lock();
// resource locked
//.usage of shared resource...

singleLock.Unlock();
```

> [!NOTE]
> `CCriticalSection`, diğer MFC eşitleme sınıflardan farklı olarak, zamanlanmış bir kilit isteğinin seçeneğine sahip değildir. Ücretsiz olacak bir iş parçacığı için bekleme süresi sonsuzdur.

Bu yaklaşım dezavantajları sınıfı eklenen eşitleme nesneleri aynı sınıfa göre biraz daha yavaş olur ' dir. Ayrıca, birden fazla iş parçacığı nesnesi silebilir şansı varsa, birleştirilmiş bir yaklaşım her zaman çalışmayabilir. Bu durumda, ayrı bir eşitleme nesneleri korumak iyidir.

Farklı durumlarda kullanılacak hangi eşitleme sınıfını belirleme hakkında daha fazla bilgi için bkz [çoklu iş parçacığı kullanımı: Zaman eşitleme sınıflarını kullanma](multithreading-when-to-use-the-synchronization-classes.md). Eşitleme hakkında daha fazla bilgi için bkz. [eşitleme](/windows/desktop/Sync/synchronization) Windows SDK. MFC çoklu iş parçacığı desteği hakkında daha fazla bilgi için bkz. [çoklu iş parçacığı kullanımı C++ ve MFC ile](multithreading-with-cpp-and-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)
