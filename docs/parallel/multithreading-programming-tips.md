---
title: 'Çoklu iş parçacığı kullanımı: Programlama ipuçları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], programming tips
- handle maps [C++]
- access control [C++], multithreading
- objects [C++], multiple threads and
- non-MFC threads [C++]
- threading [MFC], programming tips
- critical sections [C++]
- synchronization [C++], multithreading
- programming [C++], multithreaded
- communications [C++], between threads
- threading [C++], best practices
- troubleshooting [C++], multithreading
- Windows handle maps [C++]
ms.assetid: ad14cc70-c91c-4c24-942f-13a75e58bf8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9c4241b9257244de840db1f57c5e7abcb32f206
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="multithreading-programming-tips"></a>Çoklu İş Parçacığı Kullanımı: Programlama İpuçları
Birden çok iş parçacıklı uygulamalar verilere erişirken tek iş parçacıklı uygulamalar daha büyük dikkat gerektirir. Olduğundan birden çok, yürütme bağımsız yollar aynı anda birden çok iş parçacıklı uygulamalarda algoritmalar, verilerini ya da her ikisini de bilmeniz gerekir bu verileri kullanmak aynı anda birden çok iş parçacığı tarafından kullanılabilir. Bu konu Microsoft Foundation Class (MFC) kitaplığı ile birden çok iş parçacıklı uygulamalar programlamada olası sorunları önleme teknikleri açıklar.  
  
-   [Birden çok iş parçacıklarından nesnelere erişme](#_core_accessing_objects_from_multiple_threads)  
  
-   [MFC dışı iş parçacıklarından MFC nesnelerine erişme](#_core_accessing_mfc_objects_from_non.2d.mfc_threads)  
  
-   [Windows tanıtıcı eşlemeleri](#_core_windows_handle_maps)  
  
-   [İş parçacıkları arasında iletişim](#_core_communicating_between_threads)  
  
##  <a name="_core_accessing_objects_from_multiple_threads"></a> Birden çok iş parçacıklarından nesnelere erişme  
 Boyutu ve Performans nedeniyle, MFC nesneleri nesne düzeyinde, yalnızca sınıf düzeyinde iş parçacığı açısından güvenli değildir. Bu iki farklı düzenleme iki ayrı iş parçacığı olduğu anlamına gelir `CString` nesneleri, ancak aynı düzenleme olmayan iki iş parçacığı `CString` nesnesi. Birden çok iş parçacığı aynı nesne düzenleme kesinlikle görüntülenmesi gerekiyorsa, bu tür erişim kritik bölümler gibi uygun Win32 eşitleme mekanizmaları ile koruyun. İlgili nesneler kritik bölümler ve diğer hakkında daha fazla bilgi için bkz: [eşitleme](http://msdn.microsoft.com/library/windows/desktop/ms686353) içinde [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 Sınıf kitaplığı kritik bölümler hata ayıklama bellek ayırma tarafından kullanılanlar gibi genel veri yapılarını korumak için dahili olarak kullanır.  
  
##  <a name="_core_accessing_mfc_objects_from_non.2d.mfc_threads"></a> MFC dışı iş parçacıklarından MFC nesnelerine erişme  
 Bir iş parçacığı kullanma dışındaki bir şekilde oluşturan birden çok iş parçacıklı bir uygulamanız varsa, bir [CWinThread](../mfc/reference/cwinthread-class.md) nesnesi, bu iş parçacığından diğer MFC nesneleri erişemiyor. Diğer bir deyişle, ikincil bir iş parçacığından bir MFC nesnesine erişmek isterseniz, açıklanan yöntemlerden biri ile o iş parçacığı oluşturmalısınız [çoklu iş parçacığı kullanımı: kullanıcı arabirimi iş parçacıkları oluşturma](../parallel/multithreading-creating-user-interface-threads.md) veya [çoklu iş parçacığı kullanımı: Çalışan iş parçacıkları oluşturma](../parallel/multithreading-creating-worker-threads.md). Bu yöntemler birden çok iş parçacıklı uygulamaları işlemek için gerekli iç değişkenlerini başlatmak sınıf kitaplığı sağlayan yalnızca olanlardır.  
  
##  <a name="_core_windows_handle_maps"></a> Windows tanıtıcı eşlemeleri  
 Genel kural olarak, bir iş parçacığı oluşturan MFC nesneleri erişebilir. Geçici ve kalıcı Windows tanıtıcı eşlemeleri birden çok iş parçacığı erişimlerinden koruma sağlanmasına yardımcı olmak için iş parçacığı yerel depolaması tutulur olmasıdır. Örneğin, bir çalışan iş parçacığı olamaz bir hesaplama gerçekleştiren, ardından bir belgenin çağıran `UpdateAllViews` değiştirilmiş yeni verilerin görünümleri içeren windows için üye işlevi. Bu, çünkü etkisizdir eşlemesinden `CWnd` nesneleri `HWND`s'dir birincil iş parçacığı yerel. Bu bir iş parçacığı Windows tanıtıcı eşlemeyi C++ nesnesine sahip olabilir, ancak başka bir iş parçacığı aynı tanıtıcıyı farklı bir C++ nesneye eşleyebilir anlamına gelir. Bir iş parçacığı yapılan değişiklikler diğer yansıtılmaz.  
  
 Bu sorunu gidermek için birkaç yol vardır. İlk bağımsız tanıtıcıları geçirmektir (gibi bir `HWND`) çalışan iş parçacığı C++ nesneleri yerine. Çalışan iş parçacığı sonra bu nesneleri geçici eşlemesine uygun çağırarak ekler `FromHandle` üye işlevi. Çağırarak iş parçacığının kalıcı eşlemesine nesne ekleyebilirsiniz **Attach**, ancak yalnızca, nesnenin iş parçacığı daha uzun bulunacağı garanti varsa Bunun yapılması gerekir.  
  
 Çalışan iş parçacığı gerçekleştirme ve bu iletiler uygulamanın ana penceresine sonrası farklı görevler için karşılık gelen yeni kullanıcı tanımlı iletileri oluşturmak için başka bir yöntemdir kullanarak **:: PostMessage**. Bu iletişim yöntemi, her iki iş parçacığı aynı adres alanında yürütüldüğünü dışında konuşmaya iki farklı uygulama benzer.  
  
 Tanıtıcı eşlemeleri hakkında daha fazla bilgi için bkz: [Teknik Not 3](../mfc/tn003-mapping-of-windows-handles-to-objects.md). İş parçacığı yerel depolaması hakkında daha fazla bilgi için bkz: [iş parçacığı yerel depolaması](http://msdn.microsoft.com/library/windows/desktop/ms686749) ve [kullanarak iş parçacığı yerel depolama](http://msdn.microsoft.com/library/windows/desktop/ms686991) içinde [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
##  <a name="_core_communicating_between_threads"></a> İş parçacıkları arasında iletişim  
 MFC birkaç iş parçacığı güvenliği korumak için nesnelerine erişimi eşitlemek için iş parçacığı izin sınıfları sağlar. Bu sınıfların kullanımı açıklanmaktadır [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../parallel/multithreading-how-to-use-the-synchronization-classes.md) ve [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma zamanı](../parallel/multithreading-when-to-use-the-synchronization-classes.md). Bu nesneler hakkında daha fazla bilgi için bkz: [eşitleme](http://msdn.microsoft.com/library/windows/desktop/ms686353) içinde [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](../parallel/multithreading-with-cpp-and-mfc.md)