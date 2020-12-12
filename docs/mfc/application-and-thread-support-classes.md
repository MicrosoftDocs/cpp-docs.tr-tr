---
description: 'Daha fazla bilgi edinin: uygulama ve Iş parçacığı destek sınıfları'
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
ms.openlocfilehash: 89ab6e324a777c272dcbcfabc746c03cb6731589
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176749"
---
# <a name="application-and-thread-support-classes"></a>Uygulama ve İş Parçacığı Destek Sınıfları

Her uygulamanın bir ve yalnızca bir uygulama nesnesi vardır; Bu nesne çalışan programdaki diğer nesneleri koordine eder ve öğesinden türetilir `CWinApp` .

Microsoft Foundation Class (MFC) kitaplığı, bir uygulama içinde birden çok yürütme iş parçacığını destekler. Tüm uygulamaların en az bir iş parçacığı olmalıdır; nesneniz tarafından kullanılan iş parçacığı `CWinApp` Bu birincil iş parçacığıdır.

`CWinThread` işletim sisteminin iş parçacığı oluşturma yeteneklerini bir bölümünü kapsüller. Birden çok iş parçacığını daha kolay hale getirmek için MFC, Win32 eşitleme nesnelerine bir C++ arabirimi sağlamak üzere eşitleme nesnesi sınıfları da sağlar.

## <a name="application-and-thread-classes"></a>Uygulama ve Iş parçacığı sınıfları

[CWinApp](reference/cwinapp-class.md)<br/>
Uygulamayı başlatmak, çalıştırmak ve sonlandırmak için kodu kapsüller. Uygulama nesneniz bu sınıftan türetilecektir.

[CWinThread](reference/cwinthread-class.md)<br/>
Tüm iş parçacıkları için temel sınıf. Doğrudan kullanın veya `CWinThread` İş parçacığınıza Kullanıcı arabirimi işlevleri gerçekleştirdiğinde öğesinden bir sınıf türetebilirsiniz. `CWinApp` , öğesinden türetilir `CWinThread` .

## <a name="synchronization-object-classes"></a>Eşitleme nesnesi sınıfları

[CSyncObject](reference/csyncobject-class.md)<br/>
Eşitleme nesnesi sınıflarının temel sınıfı.

[Ckritiksection](reference/ccriticalsection-class.md)<br/>
Tek bir işlem içinde yalnızca bir iş parçacığının bir nesneye erişmesine izin veren bir eşitleme sınıfı.

[Csemafor](reference/csemaphore-class.md)<br/>
Bir nesne için bir ve belirtilen en fazla eşzamanlı erişim sayısı arasında izin veren bir eşitleme sınıfı.

[CMutex](reference/cmutex-class.md)<br/>
Bir nesneye erişmek için herhangi bir sayıda işlem içinde yalnızca bir iş parçacığına izin veren bir eşitleme sınıfı.

[CEvent](reference/cevent-class.md)<br/>
Bir olay oluştuğunda uygulamaya bildirimde bulunan bir eşitleme sınıfı.

[CSingleLock](reference/csinglelock-class.md)<br/>
Bir eşitleme nesnesinde kilitlemek için iş parçacığı güvenli sınıflarının üye işlevlerinde kullanılır.

[CMultiLock](reference/cmultilock-class.md)<br/>
Bir veya daha fazla eşitleme nesnesini bir dizi eşitleme nesnesinden kilitlemek için iş parçacığı güvenli sınıflarının üye işlevlerinde kullanılır.

## <a name="related-classes"></a>İlgili sınıflar

[CCommandLineInfo](reference/ccommandlineinfo-class.md)<br/>
Programınızın başlatıldığı komut satırını ayrıştırır.

[CWaitCursor](reference/cwaitcursor-class.md)<br/>
Ekranda bir bekleme imleci koyar. Uzun işlemler sırasında kullanılır.

[CDockState](reference/cdockstate-class.md)<br/>
Denetim çubukları için yerleştirme durumu verilerinin kalıcı depolamayı işler.

[CRecentFileList](reference/crecentfilelist-class.md)<br/>
En son kullanılan (MRU) dosya listesini korur.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
