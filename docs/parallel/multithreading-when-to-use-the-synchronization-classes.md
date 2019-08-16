---
title: 'Çoklu iş parçacığı kullanımı: MFC eşitleme sınıfları ne zaman kullanılır?'
ms.date: 08/27/2018
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
ms.openlocfilehash: cb68487e036093ce4718c39c18c9d1e75afe0f7c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69512004"
---
# <a name="multithreading-when-to-use-the-mfc-synchronization-classes"></a>Çoklu iş parçacığı kullanımı: MFC eşitleme sınıfları ne zaman kullanılır?

MFC ile birlikte sunulan çok iş parçacıklı sınıflar iki kategoriye ayrılır: eşitleme nesneleri ([CSyncObject](../mfc/reference/csyncobject-class.md), [csemafor](../mfc/reference/csemaphore-class.md), [CMutex](../mfc/reference/cmutex-class.md), [ccriticalhandle bölümü](../mfc/reference/ccriticalsection-class.md)ve [CEvent](../mfc/reference/cevent-class.md)) ve eşitleme erişim nesneleri ([ CMultiLock](../mfc/reference/cmultilock-class.md) ve [CSingleLock](../mfc/reference/csinglelock-class.md)).

Kaynak bütünlüğünü sağlamak için bir kaynağa erişim denetlenmesi gerektiğinde eşitleme sınıfları kullanılır. Bu denetlenen kaynaklara erişim kazanmak için eşitleme erişim sınıfları kullanılır. Bu konuda her sınıfın ne zaman kullanılacağı açıklanmaktadır.

Hangi eşitleme sınıfını kullanacağınızı öğrenmek için aşağıdaki soru dizisine sorun.

1. Uygulamanın kaynağa erişmeden önce bir şeyin gerçekleşmesini beklemek zorunda olur (örneğin, bir dosyaya yazılmadan önce bir iletişim bağlantı noktasından veri alınması gerekir)?

   Yanıt Evet ise, `CEvent`kullanın.

2. Aynı uygulama içindeki birden fazla iş parçacığı aynı anda bu kaynağa erişebilsin (örneğin, uygulamanız aynı belgede görünümlerde en fazla beş pencere sağlar)?

   Yanıt Evet ise, `CSemaphore`kullanın.

3. Birden fazla uygulama bu kaynağı kullanıyor olabilir (örneğin, kaynak bir DLL içinde)?

   Yanıt Evet ise, `CMutex`kullanın.

   Hayır ise, kullanın `CCriticalSection`.

`CSyncObject`hiçbir şekilde doğrudan kullanılmaz. Bu, diğer dört eşitleme sınıfı için temel sınıftır.

## <a name="example-1-using-three-synchronization-classes"></a>Örnek 1: Üç eşitleme sınıfı kullanma

Örnek olarak, bağlı firmaların listesini tutan bir uygulama alın. Bu uygulama, ayrı Windows 'da en fazla üç hesap incelenmesine izin verir, ancak yalnızca bir tane belirli bir zamanda güncelleştirilebilen olabilir. Bir hesap güncelleştirildiği zaman, güncelleştirilmiş veriler ağ üzerinden bir veri arşivine gönderilir.

Bu örnek uygulama, üç tür eşitleme sınıfını kullanır. Tek seferde en fazla üç hesap incelendiğinden, bu, üç görünüm nesnesine erişimi sınırlandırmak `CSemaphore` için kullanır. Dördüncü bir hesabı görüntüleme denemesi gerçekleştiğinde, uygulama ilk üç Windows 'un kapanmasından veya başarısız olana kadar bekler. Bir hesap güncelleştirildiği zaman, uygulama aynı anda yalnızca `CCriticalSection` bir hesabın güncelleştirildiğinden emin olmak için kullanır. Güncelleştirme başarılı `CEvent`olduktan sonra, olayın sinyallerine bekleyen bir iş parçacığını serbest bırakır. Bu iş parçacığı veri arşivine yeni verileri gönderir.

## <a name="example-2-using-synchronization-access-classes"></a>Örnek 2: Eşitleme erişim sınıflarını kullanma

Kullanılacak eşitleme erişim sınıfının seçilmesi de daha basittir. Uygulamanız yalnızca tek denetimli bir kaynağa erişimle ilgileniyorsa, kullanın `CSingleLock`. Bir dizi denetimli kaynağın herhangi birine erişmesi gerekiyorsa kullanın `CMultiLock`. Örnek 1 ' de `CSingleLock` , her durumda belirli bir zamanda yalnızca bir kaynak gerektiğinden, kullanılır.

Eşitleme sınıflarının nasıl kullanıldığı hakkında bilgi için bkz [. çoklu iş parçacığı: Eşitleme sınıflarını](multithreading-how-to-use-the-synchronization-classes.md)kullanma. Eşitleme hakkında daha fazla bilgi için Windows SDK [eşitleme](/windows/win32/Sync/synchronization) konusuna bakın. MFC 'de çoklu iş parçacıklı destek hakkında bilgi için bkz. [Çoklu Iş parçacığı C++ ve MFC](multithreading-with-cpp-and-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)
