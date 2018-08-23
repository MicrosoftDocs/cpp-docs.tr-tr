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
ms.openlocfilehash: 2ad830117323aef807fcebc1ef61b4dfb1900bd9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591317"
---
# <a name="multithreading-programming-tips"></a>Çoklu İş Parçacığı Kullanımı: Programlama İpuçları
Çok iş parçacıklı uygulamalar tek iş parçacıklı uygulamalar daha büyük dikkat verilere erişirken gerektirir. Olduğundan birden çok, bağımsız yürütme aynı anda birden çok iş parçacıklı uygulamalarda algoritmalar, verileri veya her ikisi de bilmelisiniz verileri yollarında aynı anda birden fazla iş parçacığı tarafından kullanılabilir. Bu konu, çok iş parçacıklı uygulamalarda Microsoft Foundation Class (MFC) kitaplığı programlama yaparken olası sorunları önleme teknikleri açıklar.  
  
- [Birden fazla iş parçacığından nesnelere erişme](#_core_accessing_objects_from_multiple_threads)  
  
- [MFC dışı iş parçacıklarından MFC nesnelere erişme](#_core_accessing_mfc_objects_from_non.2d.mfc_threads)  
  
- [Windows tanıtıcı eşlemeleri](#_core_windows_handle_maps)  
  
- [İş parçacıkları arasında iletişim kurma](#_core_communicating_between_threads)  
  
##  <a name="_core_accessing_objects_from_multiple_threads"></a> Birden fazla iş parçacığından nesnelere erişme  
 
Boyut ve Performans nedeniyle, MFC nesneleri sınıf düzeyinde yalnızca nesne düzeyinde iş parçacığı açısından güvenli değildir. Bu iki farklı işleme iki ayrı iş parçacığı olamayacağı anlamına gelir `CString` nesneleri, ancak aynı işleme olmayan iki iş parçacığı `CString` nesne. Birden çok iş parçacığı aynı nesne düzenleme kesinlikle görüntülenmesi gerekiyorsa, kritik bölüm gibi uygun Win32 eşitleme mekanizmaları ile erişimi koruyun. İlgili nesneler ve diğer kritik bölümleri hakkında daha fazla bilgi için bkz: [eşitleme](http://msdn.microsoft.com/library/windows/desktop/ms686353) Windows SDK.  
  
Sınıf kitaplığı hata ayıklama bellek ayırma tarafından kullanılanlar gibi genel veri yapılarını korumak kritik bölümler dahili olarak kullanır.  
  
##  <a name="_core_accessing_mfc_objects_from_non.2d.mfc_threads"></a> MFC dışı iş parçacıklarından MFC nesnelere erişme  
 
Kullanarak başka bir şekilde bir iş parçacığı oluşturan bir çok iş parçacıklı uygulamanız varsa bir [CWinThread](../mfc/reference/cwinthread-class.md) nesnesi, bu iş parçacığından diğer MFC nesneleri erişemiyor. Diğer bir deyişle, her MFC nesnesinin ikincil bir iş parçacığından erişmek istiyorsanız, açıklanan yöntemlerden biri ile bu iş parçacığı oluşturmalısınız [çoklu iş parçacığı kullanımı: kullanıcı arabirimi iş parçacıkları oluşturma](../parallel/multithreading-creating-user-interface-threads.md) veya [çoklu iş parçacığı kullanımı: Çalışan iş parçacıkları oluşturma](../parallel/multithreading-creating-worker-threads.md). Bu yöntemler izin veren sınıf kitaplığının çok iş parçacıklı uygulamalar işlemek için gerekli iç değişkenlerini başlatmak yalnızca olanlardır.  
  
##  <a name="_core_windows_handle_maps"></a> Windows tanıtıcı eşlemeleri  
 
Genel kural olarak, bir iş parçacığı oluşturan MFC nesneleri erişebilirsiniz. Bu durum, birden çok iş parçacığı erişimlerinden koruma sağlamak için iş parçacığı yerel depolama Windows tanıtıcı eşlemeleri geçici ve kalıcı tutulur çünkü. İş parçacığı gibi olamaz ve bir hesaplama gerçekleştirmek sonra belgenin çağrı `UpdateAllViews` değiştiren yeni verilerin görünümlerini içeren windows için üye işlevi. Bu, çünkü etkisizdir eşlemesinden `CWnd` Cwnd'lerden için nesneleri, birincil iş parçacığına yerel. Bu, tek bir iş parçacığı bir C++ nesnesi için bir Windows tanıtıcı eşlemeyi olabilir, ancak başka bir iş parçacığı için farklı bir C++ nesnesi aynı tanıtıcıyı eşleyebilir anlamına gelir. Bir iş parçacığında yapılan değişiklikler diğer yansıtılmaz.  
  
Bu sorunu gidermek için birkaç yol vardır. İlk tek tek işler (örneğin, bir HWND) çalışan iş parçacığı C++ nesneleri yerine geçirmektir. Çalışan iş parçacığı ardından bu nesneleri geçici eşlemesine uygun çağırarak ekler `FromHandle` üye işlevi. Çağırarak iş parçacığının kalıcı haritaya nesne ekleyebilirsiniz `Attach`, ancak yalnızca nesne iş parçacığı artık mevcut garanti edilir, bunun yapılması gerekir.  
  
Farklı görevler, çalışan iş parçacıkları gerçekleştirme ve uygulamanın ana pencere için bu ileti göndermek için karşılık gelen yeni kullanıcı tanımlı iletileri oluşturmak için başka bir yöntemdir kullanarak `::PostMessage`. Bu yöntem iletişim dışında her iki iş parçacığı aynı adres alanında yürütülen konuşmaya iki farklı uygulamalara benzerdir.  
  
Tanıtıcı eşlemeleri hakkında daha fazla bilgi için bkz. [Teknik Not 3](../mfc/tn003-mapping-of-windows-handles-to-objects.md). İş parçacığı yerel depolama hakkında daha fazla bilgi için bkz. [iş parçacığında yerel depolama](http://msdn.microsoft.com/library/windows/desktop/ms686749) ve [kullanarak iş parçacığı yerel depolama](http://msdn.microsoft.com/library/windows/desktop/ms686991) Windows SDK.  
  
##  <a name="_core_communicating_between_threads"></a> İş parçacıkları arasında iletişim kurma  
 
MFC, birkaç iş parçacığı güvenliği sağlamak için nesnelere erişimi eşitlemek için iş parçacığı izin sınıflar sağlar. Bu sınıfların kullanımı, açıklanan [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../parallel/multithreading-how-to-use-the-synchronization-classes.md) ve [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma zamanı](../parallel/multithreading-when-to-use-the-synchronization-classes.md). Bu nesneler hakkında daha fazla bilgi için bkz: [eşitleme](http://msdn.microsoft.com/library/windows/desktop/ms686353) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](../parallel/multithreading-with-cpp-and-mfc.md)