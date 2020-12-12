---
description: 'Iş parçacığı oluşturma hakkında daha fazla bilgi edinin: MFC eşitleme sınıfları ne zaman kullanılır?'
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
ms.openlocfilehash: 02776bc61ed702ee81ce0f7373dd442a9fc3d446
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149857"
---
# <a name="multithreading-when-to-use-the-mfc-synchronization-classes"></a>Çoklu iş parçacığı kullanımı: MFC eşitleme sınıfları ne zaman kullanılır?

MFC ile birlikte sunulan çok iş parçacıklı sınıflar iki kategoriye ayrılır: eşitleme nesneleri ([CSyncObject](../mfc/reference/csyncobject-class.md), [csemafor](../mfc/reference/csemaphore-class.md), [CMutex](../mfc/reference/cmutex-class.md), [ccriticalhandle bölümü](../mfc/reference/ccriticalsection-class.md)ve [CEvent](../mfc/reference/cevent-class.md)) ve eşitleme erişim nesneleri ([CMultiLock](../mfc/reference/cmultilock-class.md) ve [CSingleLock](../mfc/reference/csinglelock-class.md)).

Kaynak bütünlüğünü sağlamak için bir kaynağa erişim denetlenmesi gerektiğinde eşitleme sınıfları kullanılır. Bu denetlenen kaynaklara erişim kazanmak için eşitleme erişim sınıfları kullanılır. Bu konuda her sınıfın ne zaman kullanılacağı açıklanmaktadır.

Hangi eşitleme sınıfını kullanacağınızı öğrenmek için aşağıdaki soru dizisine sorun.

1. Uygulamanın kaynağa erişmeden önce bir şeyin gerçekleşmesini beklemek zorunda olur (örneğin, bir dosyaya yazılmadan önce bir iletişim bağlantı noktasından veri alınması gerekir)?

   Yanıt Evet ise, kullanın `CEvent` .

2. Aynı uygulama içindeki birden fazla iş parçacığı aynı anda bu kaynağa erişebilsin (örneğin, uygulamanız aynı belgede görünümlerde en fazla beş pencere sağlar)?

   Yanıt Evet ise, kullanın `CSemaphore` .

3. Birden fazla uygulama bu kaynağı kullanıyor olabilir (örneğin, kaynak bir DLL içinde)?

   Yanıt Evet ise, kullanın `CMutex` .

   Hayır ise, kullanın `CCriticalSection` .

`CSyncObject` hiçbir şekilde doğrudan kullanılmaz. Bu, diğer dört eşitleme sınıfı için temel sınıftır.

## <a name="example-1-using-three-synchronization-classes"></a>Örnek 1: üç eşitleme sınıfı kullanma

Örnek olarak, bağlı firmaların listesini tutan bir uygulama alın. Bu uygulama, ayrı Windows 'da en fazla üç hesap incelenmesine izin verir, ancak yalnızca bir tane belirli bir zamanda güncelleştirilebilen olabilir. Bir hesap güncelleştirildiği zaman, güncelleştirilmiş veriler ağ üzerinden bir veri arşivine gönderilir.

Bu örnek uygulama, üç tür eşitleme sınıfını kullanır. Tek seferde en fazla üç hesap incelendiğinden, bu, `CSemaphore` üç görünüm nesnesine erişimi sınırlandırmak için kullanır. Dördüncü bir hesabı görüntüleme denemesi gerçekleştiğinde, uygulama ilk üç Windows 'un kapanmasından veya başarısız olana kadar bekler. Bir hesap güncelleştirildiği zaman, uygulama `CCriticalSection` aynı anda yalnızca bir hesabın güncelleştirildiğinden emin olmak için kullanır. Güncelleştirme başarılı olduktan sonra, `CEvent` olayın sinyallerine bekleyen bir iş parçacığını serbest bırakır. Bu iş parçacığı veri arşivine yeni verileri gönderir.

## <a name="example-2-using-synchronization-access-classes"></a>Örnek 2: eşitleme erişim sınıflarını kullanma

Kullanılacak eşitleme erişim sınıfının seçilmesi de daha basittir. Uygulamanız yalnızca tek denetimli bir kaynağa erişimle ilgileniyorsa, kullanın `CSingleLock` . Bir dizi denetimli kaynağın herhangi birine erişmesi gerekiyorsa kullanın `CMultiLock` . Örnek 1 ' de, `CSingleLock` her durumda belirli bir zamanda yalnızca bir kaynak gerektiğinden, kullanılır.

Eşitleme sınıflarının nasıl kullanıldığı hakkında bilgi için bkz. [Çoklu Iş parçacığı kullanımı: eşitleme sınıflarını kullanma](multithreading-how-to-use-the-synchronization-classes.md). Eşitleme hakkında daha fazla bilgi için Windows SDK [eşitleme](/windows/win32/Sync/synchronization) konusuna bakın. MFC 'de çoklu iş parçacıklı destek hakkında bilgi için bkz. [Çoklu Iş parçacığı C++ ve MFC](multithreading-with-cpp-and-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)
