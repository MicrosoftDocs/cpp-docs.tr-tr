---
title: 'Çoklu iş parçacığı kullanımı: Ne zaman MFC eşitleme sınıflarını kullanma'
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
ms.openlocfilehash: 72cf5310704c1ae959cc012146a03dd32cff4068
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407659"
---
# <a name="multithreading-when-to-use-the-mfc-synchronization-classes"></a>Çoklu iş parçacığı kullanımı: Ne zaman MFC eşitleme sınıflarını kullanma

MFC ile sunulan çok iş parçacıklı sınıfları iki kategoriye ayrılır: eşitleme nesneleri ([CSyncObject](../mfc/reference/csyncobject-class.md), [CSemaphore](../mfc/reference/csemaphore-class.md), [CMutex](../mfc/reference/cmutex-class.md), [ CCriticalSection](../mfc/reference/ccriticalsection-class.md), ve [CEvent](../mfc/reference/cevent-class.md)) ve eşitleme erişim nesneleri ([CMultiLock](../mfc/reference/cmultilock-class.md) ve [CSingleLock](../mfc/reference/csinglelock-class.md)).

Eşitleme sınıfları, kaynak bütünlüğünü sağlamak için bir kaynağa erişim denetlenmesi kullanılır. Eşitleme erişim sınıfları, denetlenen bu kaynaklara erişmek için kullanılır. Bu konu ne zaman her sınıf kullanılacağını açıklar.

Hangi eşitleme sınıfını kullanmanız gerektiğini belirlemek için aşağıdaki dizi soru sorun:

1. Uygulama bir kaynağa erişmeden önce olmasını beklemek zorunda olmadığını (önce bir dosyaya yazılır Örneğin, veri iletişim bağlantı noktasından alınması gerekir)?

   Yanıt Evet ise kullanın `CEvent`.

2. Birden fazla aynı uygulama erişimi içinde bu kaynağı tek seferde iş parçacığı (örneğin, uygulamanızın en fazla beş windows aynı belgede görünümlerle sağlar)?

   Yanıt Evet ise kullanın `CSemaphore`.

3. Bu kaynak birden fazla uygulamayı kullanabilirsiniz (örneğin, kaynak DLL içinde'dır)?

   Yanıt Evet ise kullanın `CMutex`.

   Hayır ise, kullanın `CCriticalSection`.

`CSyncObject` hiçbir zaman doğrudan kullanılmaz. Diğer dört eşitleme sınıfları için temel sınıftır.

## <a name="example-1-using-three-synchronization-classes"></a>Örnek 1: Üç eşitleme sınıfını kullanma

Örneğin, bağlantılı hesaplar listesini tutar uygulamanın yararlanın. Bu uygulamanın ayrı windows incelenmesi için en fazla üç hesapları sağlar, ancak belirli bir zamanda yalnızca biri güncelleştirilebilir. Bir hesap güncelleştirildiğinde güncelleştirilen verileri bir veri arşivine ağ üzerinden gönderilir.

Bu örnek uygulama, üç tür eşitleme sınıfları kullanır. Aynı anda incelenecek en fazla üç hesapları izin verdiğinden, kullandığı `CSemaphore` üç görünüm nesnelerine erişimi sınırlamak için. Görüntüleme girişiminde dördüncü bir hesabı meydana gelir, ilk üç windows birini kapatır veya başarısız kadar bekler ya da uygulama. Bir hesap güncelleştirildiğinde uygulamanın kullandığı `CCriticalSection` aynı anda yalnızca bir hesap güncelleştirildiğinden emin olmak için. Güncelleştirme başarılı olduktan sonra bildirir `CEvent`, sinyal olayı için bekleyen bir iş parçacığını serbest bırakır. Bu iş parçacığı veri arşivine yeni verileri gönderir.

## <a name="example-2-using-synchronization-access-classes"></a>Örnek 2: Eşitleme erişim sınıfları kullanma

Hangi eşitleme erişimi sınıfını kullanmak için daha kolay seçme. Uygulamanız yalnızca tek bir denetimli kaynak erişimi ile ilgili kullanırsanız `CSingleLock`. Bir dizi denetimli kaynak herhangi birine erişmesi gerekiyorsa kullanın `CMultiLock`. Örnek 1'de, `CSingleLock` her durumda belirli bir zamanda yalnızca bir kaynak gerektiğinden, kullanılabilirdi.

Eşitleme sınıfları nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [çoklu iş parçacığı kullanımı: Eşitleme sınıflarının nasıl kullanılacağını](multithreading-how-to-use-the-synchronization-classes.md). Eşitleme hakkında daha fazla bilgi için bkz: [eşitleme](/windows/desktop/Sync/synchronization) Windows SDK. MFC çoklu iş parçacığı desteği hakkında daha fazla bilgi için bkz: [çoklu iş parçacığı kullanımı C++ ve MFC ile](multithreading-with-cpp-and-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)
