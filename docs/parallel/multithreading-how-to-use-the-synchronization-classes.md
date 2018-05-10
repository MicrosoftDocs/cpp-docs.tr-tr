---
title: 'Çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma konusunda | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49b0737a794216c4899b280bc049a1cdc0fe0948
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="multithreading-how-to-use-the-synchronization-classes"></a>Çoklu İş Parçacığı Kullanımı: Eşitleme Sınıflarını Kullanma
İş parçacıkları arasında kaynak erişim eşitleme bir ortak birden çok iş parçacıklı uygulamalar yazılırken sorunudur. İki veya daha fazla sahip aynı anda aynı veri istenmeyen ve beklenmeyen sonuçlara yol açabilir erişim iş parçacıkları. Örneğin, başka bir iş parçacığı aynı yapısını içeriğini okuma sırasında bir iş parçacığı yapının içeriklerini güncelleştirme. Hangi veriyi okuma iş parçacığının alacağı bilinmiyor: eski verileri, yeni yazılmış verileri veya muhtemelen her ikisinin bir karışımıyla. MFC bir dizi eşitleme ve bu sorunun çözümüne yardımcı olmak için eşitleme erişim sınıfları sağlar. Bu konu, mevcut sınıfları ve bunları tipik birden çok iş parçacıklı uygulamada iş parçacığı açısından güvenli sınıflar oluşturmak için nasıl kullanılacağını açıklar.  
  
 Tipik bir birden çok iş parçacıklı uygulama iş parçacıkları arasında paylaşılacak bir kaynağı temsil eden bir sınıf sahiptir. Düzgün bir şekilde tasarlanmış, tamamen iş parçacığı açısından güvenli sınıf, herhangi bir eşitleme işlevi çağırmak gerektirmez. Her şeyi sınıfına nasıl en iyi nasıl, bozulmuş konusunda olmamasından sınıfı odaklanmasına olanak sağlayarak dahili olarak işlenir. Tam olarak iş parçacığı açısından güvenli sınıf oluşturmak için etkin bir yöntem eşitleme sınıfını kaynak sınıfıyla birleştirme göstermektir. Eşitleme sınıfları paylaşılan sınıfta birleştirilmesi bir işlemdir.  
  
 Örnek olarak, bağlantılı hesapları listesini tutar bir uygulama olur. Bu uygulamanın ayrı windows incelenmesi en çok üç hesapları sağlar, ancak belirli bir zamanda yalnızca biri güncelleştirilebilir. Bir hesap güncelleştirildiğinde, güncelleştirilen verileri bir veri arşivine ağ üzerinden gönderilir.  
  
 Bu örnek uygulama üç tür eşitleme sınıfları kullanır. Bir kerede incelenmesi en çok üç hesapları izin verdiğinden, kullanan [CSemaphore](../mfc/reference/csemaphore-class.md) üç Görünüm nesnesine erişimi sınırlamak için. Görüntüleme girişiminde dördüncü bir hesabın oluşur, ilk üç windows birini kapatır veya başarısız kadar bekler ya da uygulama. Bir hesap güncelleştirildiğinde uygulamanın kullandığı [CCriticalSection](../mfc/reference/ccriticalsection-class.md) aynı anda yalnızca bir hesap güncelleştirildiğinden emin olmak için. Güncelleştirme başarılı olduktan sonra sinyalleri [CEvent](../mfc/reference/cevent-class.md), olay bildirilmesini bekleyen bir iş parçacığını serbest bırakır. Bu iş parçacığı yeni verileri veri arşivine gönderir.  
  
##  <a name="_mfc_designing_a_thread.2d.safe_class"></a> Bir iş parçacığı açısından güvenli sınıf tasarımı  
 Bir sınıf tam olarak iş parçacığı açısından güvenli hale getirmek için önce uygun eşitleme sınıfını paylaşılan sınıflara bir veri üyesi olarak ekleyin. Önceki örnekte hesap yönetimi, bir **CSemaphore** veri üyesi görünüm sınıfına eklenen bir `CCriticalSection` veri üyesi bağlantılı liste sınıfına eklenmesi ve bir `CEvent` veri üyesi verileri eklenmesi depolama sınıfı.  
  
 Ardından sınıftaki verileri değiştiren veya kontrollü bir kaynağa erişen tüm üye işlevlerine eşitleme çağrıları ekleyin. Her işlevinde, ya da oluşturmalısınız bir [CSingleLock](../mfc/reference/csinglelock-class.md) veya [CMultiLock](../mfc/reference/cmultilock-class.md) nesne ve o nesnenin çağrı `Lock` işlevi. Kilit nesnesi kapsam dışında gider ve yok, nesnenin yıkıcı çağrıları `Unlock` sizin için kaynak serbest bırakma. Elbette, çağırabilirsiniz `Unlock` doğrudan istiyorsanız.  
  
 Bu şekilde, iş parçacığı açısından güvenli sınıf tasarımı birden çok iş parçacıklı bir uygulamaya bir iş parçacığı güvenli olmayan sınıf olarak kolayca, ancak daha yüksek düzeyde güvenlik ile kullanılmak üzere sağlar. Eşitleme nesnesi ve eşitleme erişimi nesnesini kaynağın sınıfına yalıtma eşitleme kodunu sürdürme dezavantajı olmadan tam olarak iş parçacığı açısından güvenli programlama tüm avantajlarını sağlar.  
  
 Aşağıdaki kod örneğinde, bir veri üyesi kullanarak bu yöntem gösterilmektedir `m_CritSection` (türünde `CCriticalSection`), paylaşılan bir kaynak sınıfında bildirilen ve `CSingleLock` nesne. Paylaşılan kaynağı eşitleme (türetilmiş `CWinThread`) oluşturarak denenir bir `CSingleLock` nesnesinin adresini kullanarak `m_CritSection` nesnesi. Kaynağı kilitlemek için bir girişimde ve aldığınızda, iş paylaşılan nesne üzerinde gerçekleştirilir. İş tamamlandığında, kaynak çağrısıyla kilidi açılmış `Unlock`.  
  
```  
CSingleLock singleLock(&m_CritSection);  
singleLock.Lock();  
// resource locked  
//.usage of shared resource...  
  
singleLock.Unlock();  
```  
  
> [!NOTE]
>  `CCriticalSection`, diğer MFC eşitleme sınıfları, zamanlanmış kilitleme isteğine seçeneği yok. Serbest hale için bir iş parçacığı için bekleme süresi sonsuz olur.  
  
 Bu yaklaşımın dezavantajları sınıfı eşitleme nesneleri eklenmemiş aynı sınıfı biraz daha yavaş olacaktır ' dir. Ayrıca, birden çok iş parçacığı nesne silebilir şansı ise, birleştirilmiş bir yaklaşım her zaman çalışmayabilir. Bu durumda, ayrı eşitleme nesneleri korumak daha iyi olur.  
  
 Farklı durumlarda kullanılacak hangi eşitleme sınıfının belirleme hakkında daha fazla bilgi için bkz: [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma zamanı](../parallel/multithreading-when-to-use-the-synchronization-classes.md). Eşitleme hakkında daha fazla bilgi için bkz: [eşitleme](http://msdn.microsoft.com/library/windows/desktop/ms686353) içinde [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]. MFC çoklu iş parçacığı desteği hakkında daha fazla bilgi için bkz: [C++ ve MCF ile çoklu iş parçacığı kullanımı](../parallel/multithreading-with-cpp-and-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](../parallel/multithreading-with-cpp-and-mfc.md)