---
title: Uygulama ve İş Parçacığı Destek Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.support
helpviewer_keywords:
- application objects [MFC], thread support classes
- lock classes [MFC]
- thread support classes [MFC]
- threading [MFC]
- synchronization classes [MFC], multithreading
- application support classes [MFC]
ms.assetid: 3c1d14fd-c35c-48f1-86ce-1e0f9a32c36d
ms.openlocfilehash: 667725a60fb0c907a9c2d017674f9d097d1f4946
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262046"
---
# <a name="application-and-thread-support-classes"></a>Uygulama ve İş Parçacığı Destek Sınıfları

Her uygulamanın bir ve yalnızca bir uygulama nesnesi vardır; Bu nesne, çalışan bir program içindeki diğer nesnelerin koordinatları ve türetilen `CWinApp`.

Microsoft Foundation Class (MFC) kitaplığı yürütme uygulama içinde birden çok iş parçacığı destekler. Tüm uygulamaların, en az bir iş parçacığı olması gerekir; tarafından kullanılan iş parçacığı, `CWinApp` bu birincil iş parçacığı bir nesnedir.

`CWinThread` iş parçacığı özellikleri işletim sisteminin bir bölümünü kapsüller. Birden çok iş parçacığı daha kolay hale getirmek için MFC ayrıca Win32 eşitleme nesneleri için bir C++ arabirim sağlamak üzere nesne sınıfları eşitleme sağlar.

## <a name="application-and-thread-classes"></a>Uygulama ve iş parçacığı sınıfları

[CWinApp](../mfc/reference/cwinapp-class.md)<br/>
Başlatma, çalıştırmak ve uygulamayı sonlandırmak için kod kapsüller. Uygulama nesnenizin bu sınıftan türetilen.

[CWinThread](../mfc/reference/cwinthread-class.md)<br/>
Tüm iş parçacıkları için temel sınıf. Doğrudan kullanın ya da devre dışı bir sınıftan türetilen `CWinThread` , iş parçacığı kullanıcı arabirimi işlevleri uyguluyorsa. `CWinApp` türetilen `CWinThread`.

## <a name="synchronization-object-classes"></a>Eşitleme nesne sınıfları

[CSyncObject](../mfc/reference/csyncobject-class.md)<br/>
Eşitleme nesne sınıflarını temel sınıfı.

[CCriticalSection](../mfc/reference/ccriticalsection-class.md)<br/>
Bir nesneye erişmek için tek bir işlem içinde yalnızca bir iş parçacığına izin veren bir eşitleme sınıfını.

[CSemaphore](../mfc/reference/csemaphore-class.md)<br/>
Bir ve aynı anda erişen bir nesne için belirtilen en yüksek sayıda arasında izin veren bir eşitleme sınıfını.

[CMutex](../mfc/reference/cmutex-class.md)<br/>
Herhangi bir nesneye erişmek için işlem sayısı içinde yalnızca tek bir iş parçacığı izin veren bir eşitleme sınıfını.

[CEvent](../mfc/reference/cevent-class.md)<br/>
Bir uygulama bir olay gerçekleştiğinde bildiren bir eşitleme sınıfını.

[CSingleLock](../mfc/reference/csinglelock-class.md)<br/>
İş parçacığı açısından güvenli sınıfının üye fonksiyonları bir eşitleme nesnesi üzerinde kilitlemek için kullanılır.

[CMultiLock](../mfc/reference/cmultilock-class.md)<br/>
İş parçacığı açısından güvenli sınıfının üye fonksiyonları eşitleme nesneleri dizisini bir veya daha fazla eşitleme nesneleri kilitlemek için kullanılır.

## <a name="related-classes"></a>İlgili sınıflar

[CCommandLineInfo](../mfc/reference/ccommandlineinfo-class.md)<br/>
Komut satırı ile programınızın başlatıldığından ayrıştırır.

[CWaitCursor](../mfc/reference/cwaitcursor-class.md)<br/>
Bekleme imlecini ekranın koyar. Uzun işlemler sırasında kullanılır.

[CDockState](../mfc/reference/cdockstate-class.md)<br/>
Kalıcı depolama, yerleştirme denetim çubukları için eyalet verilerini işler.

[CRecentFileList](../mfc/reference/crecentfilelist-class.md)<br/>
En son kullanılan (MRU) dosya listesi tutar.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)
