---
title: Uygulama ve iş parçacığı destek sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.support
dev_langs:
- C++
helpviewer_keywords:
- application objects [MFC], thread support classes
- lock classes [MFC]
- thread support classes [MFC]
- threading [MFC]
- synchronization classes [MFC], multithreading
- application support classes [MFC]
ms.assetid: 3c1d14fd-c35c-48f1-86ce-1e0f9a32c36d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9f3877cf85e369756b15d565af1481fd6d258df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341316"
---
# <a name="application-and-thread-support-classes"></a>Uygulama ve İş Parçacığı Destek Sınıfları
Her uygulama tek bir uygulama nesnesi; yine de sahip istiyor musunuz? Bu nesne çalışan program diğer nesneleri düzenler ve türetilmiş `CWinApp`.  
  
 Microsoft Foundation Class (MFC) kitaplığı yürütme bir uygulama içinde birden çok iş parçacığı destekler. Tüm uygulamaların en az bir iş parçacığı olması gerekir; tarafından kullanılan iş parçacığı, `CWinApp` bu birincil iş parçacığı bir nesnedir.  
  
 `CWinThread` iş parçacığı özellikleri işletim sisteminin bir bölümünü yalıtır. Birden çok iş parçacığı kullanımını sağlamak için MFC ayrıca Win32 eşitleme nesneleri C++ arabirimine sağlamak için nesne sınıfları eşitleme sağlar.  
  
## <a name="application-and-thread-classes"></a>Uygulama ve iş parçacığı sınıfları  
 [CWinApp](../mfc/reference/cwinapp-class.md)  
 Başlatma, çalıştırmak ve sonlandırmak için kod yalıtır. Uygulama nesnesi bu sınıftan türeyen.  
  
 [CWinThread](../mfc/reference/cwinthread-class.md)  
 Tüm iş parçacıklarının için temel sınıf. Doğrudan kullanın ya da öğesinden bir sınıf türetin `CWinThread` , iş parçacığı kullanıcı arabirimi işlevleri uyguluyorsa. `CWinApp` türetilmiş `CWinThread`.  
  
## <a name="synchronization-object-classes"></a>Eşitleme nesne sınıfları  
 [CSyncObject](../mfc/reference/csyncobject-class.md)  
 Eşitleme nesnesi sınıfların temel sınıf.  
  
 [CCriticalSection](../mfc/reference/ccriticalsection-class.md)  
 Bir nesneye erişmek için tek bir işlem içinde yalnızca tek bir iş parçacığı sağlayan bir eşitleme sınıfı.  
  
 [CSemaphore](../mfc/reference/csemaphore-class.md)  
 Tek ve eş zamanlı erişimler bir nesne için belirtilen en yüksek sayıda arasında sağlayan bir eşitleme sınıfı.  
  
 [CMutex](../mfc/reference/cmutex-class.md)  
 Herhangi bir nesneye erişmek için işlemlerin sayısı içinde yalnızca tek bir iş parçacığı sağlayan bir eşitleme sınıfı.  
  
 [CEvent](../mfc/reference/cevent-class.md)  
 Bir uygulama bir olay gerçekleştiğinde bildiren bir eşitleme sınıfı.  
  
 [CSingleLock](../mfc/reference/csinglelock-class.md)  
 İş parçacığı açısından güvenli sınıflar üye işlevlerinde bir eşitleme nesnesinde kilitlemek için kullanılır.  
  
 [CMultiLock](../mfc/reference/cmultilock-class.md)  
 İş parçacığı açısından güvenli sınıflar üye işlevlerde eşitleme nesnelerinin bir dizisi bir veya daha fazla eşitleme nesnelerden kilitlemek için kullanılır.  
  
## <a name="related-classes"></a>İlgili sınıflar  
 [CCommandLineInfo](../mfc/reference/ccommandlineinfo-class.md)  
 Komut satırı ile programınızı başlatıldığından ayrıştırır.  
  
 [CWaitCursor](../mfc/reference/cwaitcursor-class.md)  
 Bekleme imleç ekranda koyar. Uzun işlemleri sırasında kullanılır.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 Denetim çubukları durumu verilerini yerleştirme kalıcı depolama işler.  
  
 [CRecentFileList](../mfc/reference/crecentfilelist-class.md)  
 En son kullanılan dosya listesi (MRU) korur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

