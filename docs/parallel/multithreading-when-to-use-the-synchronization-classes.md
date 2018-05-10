---
title: 'Çoklu iş parçacığı kullanımı: Eşitleme sınıflarını kullanma zamanı | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [MFC], synchronization classes
- resources [C++], multithreading
- synchronization classes [C++]
- synchronization [C++], multithreading
- controlled resource access [C++]
- synchronization access classes [C++]
- threading [C++], synchronization
- multithreading [C++], synchronization classes
ms.assetid: 4914f54e-68ac-438f-93c9-c013455a657e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b05922b826de81b5192b183e1c0afdfcda189f03
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="multithreading-when-to-use-the-synchronization-classes"></a>Çoklu İş Parçacığı Kullanımı: Eşitleme Sınıfları Ne Zaman Kullanılır?
MFC ile sağlanan birden çok iş parçacıklı sınıfları iki kategoriye ayrılır: eşitleme nesneleri ([CSyncObject](../mfc/reference/csyncobject-class.md), [CSemaphore](../mfc/reference/csemaphore-class.md), [CMutex](../mfc/reference/cmutex-class.md), [ CCriticalSection](../mfc/reference/ccriticalsection-class.md), ve [CEvent](../mfc/reference/cevent-class.md)) ve eşitleme erişim nesneler ([CMultiLock](../mfc/reference/cmultilock-class.md) ve [CSingleLock](../mfc/reference/csinglelock-class.md)).  
  
 Eşitleme sınıfları kaynak bütünlüğünü sağlamak için bir kaynağa erişim denetlenmesi olduğunda kullanılır. Eşitleme erişim sınıfları bu denetimli kaynaklara erişmek için kullanılır. Bu konuda ne zaman her sınıf kullanılacağı açıklanmaktadır.  
  
 Hangi eşitleme sınıfının kullanmanız gerektiğini belirlemek için aşağıdaki dizi soru sorun:  
  
1.  Uygulama bir kaynağa erişmeden önce olmasını beklemek zorunda (önce bir dosyaya yazılır Örneğin, veri iletişimi bağlantı noktasından alınması gerektiğini)?  
  
     Yanıt Evet ise, kullanmak `CEvent`.  
  
2.  Birden fazla içindeki aynı uygulama erişimi bu kaynak iş parçacığı tek seferde (örneğin, aynı belge üzerinde görünümleri ile en fazla beş windows uygulamanız izin verir)?  
  
     Yanıt Evet ise, kullanmak `CSemaphore`.  
  
3.  Birden fazla uygulama bu kaynak kullanabilirsiniz (örneğin, kaynak DLL içinde'dır)?  
  
     Yanıt Evet ise, kullanmak `CMutex`.  
  
     Öyle değilse, kullanmak `CCriticalSection`.  
  
 **CSyncObject** asla doğrudan kullanılmaz. Diğer dört eşitleme sınıflar için temel sınıftır.  
  
## <a name="example-1-using-three-synchronization-classes"></a>Örnek 1: Üç eşitleme sınıflarını kullanma  
 Örnek olarak, bağlantılı hesapları listesini tutar bir uygulama olur. Bu uygulamanın ayrı windows incelenmesi en çok üç hesapları sağlar, ancak belirli bir zamanda yalnızca biri güncelleştirilebilir. Bir hesap güncelleştirildiğinde, güncelleştirilen verileri bir veri arşivine ağ üzerinden gönderilir.  
  
 Bu örnek uygulama üç tür eşitleme sınıfları kullanır. Bir kerede incelenmesi en çok üç hesapları izin verdiğinden, kullanan `CSemaphore` üç Görünüm nesnesine erişimi sınırlamak için. Görüntüleme girişiminde dördüncü bir hesabın oluşur, ilk üç windows birini kapatır veya başarısız kadar bekler ya da uygulama. Bir hesap güncelleştirildiğinde uygulamanın kullandığı `CCriticalSection` aynı anda yalnızca bir hesap güncelleştirildiğinden emin olmak için. Güncelleştirme başarılı olduktan sonra sinyalleri `CEvent`, olay bildirilmesini bekleyen bir iş parçacığını serbest bırakır. Bu iş parçacığı yeni verileri veri arşivine gönderir.  
  
## <a name="example-2-using-synchronization-access-classes"></a>Örnek 2: Eşitleme erişim sınıfları kullanma  
 Kullanmak için hangi eşitleme erişim sınıfı daha kolay olduğunu belirleyin. Yalnızca tek bir kontrollü kaynağa erişme ile uygulamanızı kaygı kullanırsanız `CSingleLock`. Denetimli kaynak sayısı herhangi biri erişmesi gereken kullanırsanız `CMultiLock`. Örnek 1, `CSingleLock` her durumda belirli bir zamanda yalnızca bir kaynak gerektiğinden, kullanılabilirdi.  
  
 Eşitleme sınıfları nasıl kullanıldığı konusunda daha fazla bilgi için bkz: [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../parallel/multithreading-how-to-use-the-synchronization-classes.md). Eşitleme hakkında daha fazla bilgi için bkz: [eşitleme](http://msdn.microsoft.com/library/windows/desktop/ms686353) içinde [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]. MFC içinde çoklu iş parçacığı desteği hakkında daha fazla bilgi için bkz: [C++ ve MCF ile çoklu iş parçacığı kullanımı](../parallel/multithreading-with-cpp-and-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](../parallel/multithreading-with-cpp-and-mfc.md)