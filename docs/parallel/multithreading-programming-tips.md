---
title: 'Çoklu iş parçacığı kullanımı: MFC programlama ipuçları'
ms.date: 08/27/2018
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
ms.openlocfilehash: e89d0d534638f7216f142bc3f86633a59b8b0ff7
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290812"
---
# <a name="multithreading-mfc-programming-tips"></a>Çoklu iş parçacığı kullanımı: MFC programlama ipuçları

Çok iş parçacıklı uygulamalar tek iş parçacıklı uygulamaların operations hedeflenen sırayla birden çok iş parçacığı tarafından erişilebilen herhangi bir veri bozuk olmadığından emin olun ve daha büyük dikkat gerektirir. Bu konu, çok iş parçacıklı uygulamalarda Microsoft Foundation Class (MFC) kitaplığı programlama yaparken olası sorunları önleme teknikleri açıklar.

- [Birden fazla iş parçacığından nesnelere erişme](#_core_accessing_objects_from_multiple_threads)

- [MFC dışı iş parçacıklarından MFC nesnelere erişme](#_core_accessing_mfc_objects_from_non.2d.mfc_threads)

- [Windows tanıtıcı eşlemeleri](#_core_windows_handle_maps)

- [İş parçacıkları arasında iletişim kurma](#_core_communicating_between_threads)

##  <a name="_core_accessing_objects_from_multiple_threads"></a> Birden fazla iş parçacığından nesnelere erişme

MFC nesneleri kendileri tarafından iş parçacığı açısından güvenli değildir. MFC eşitleme sınıfları ve/veya uygun Win32 eşitleme nesneleri gibi kritik bölümler kullanmadığınız sürece, iki ayrı iş parçacığı aynı nesne kullanamazsınız. İlgili nesneler ve diğer kritik bölümleri hakkında daha fazla bilgi için bkz: [eşitleme](/windows/desktop/Sync/synchronization) Windows SDK.

Sınıf kitaplığı hata ayıklama bellek ayırma tarafından kullanılanlar gibi genel veri yapılarını korumak kritik bölümler dahili olarak kullanır.

##  <a name="_core_accessing_mfc_objects_from_non.2d.mfc_threads"></a> MFC dışı iş parçacıklarından MFC nesnelere erişme

Kullanarak başka bir şekilde bir iş parçacığı oluşturan bir çok iş parçacıklı uygulamanız varsa bir [CWinThread](../mfc/reference/cwinthread-class.md) nesnesi, bu iş parçacığından diğer MFC nesneleri erişemiyor. Diğer bir deyişle, her MFC nesnesinin ikincil bir iş parçacığından erişmek istiyorsanız, açıklanan yöntemlerden biri ile bu iş parçacığı oluşturmalısınız [çoklu iş parçacığı kullanımı: Kullanıcı arabirimi iş parçacıkları oluşturma](multithreading-creating-user-interface-threads.md) veya [çoklu iş parçacığı kullanımı: Çalışan iş parçacıkları oluşturma](multithreading-creating-worker-threads.md). Bu yöntemler izin veren sınıf kitaplığının çok iş parçacıklı uygulamalar işlemek için gerekli iç değişkenlerini başlatmak yalnızca olanlardır.

##  <a name="_core_windows_handle_maps"></a> Windows tanıtıcı eşlemeleri

Genel kural olarak, bir iş parçacığı oluşturan MFC nesneleri erişebilirsiniz. Bu durum, birden çok iş parçacığı erişimlerinden koruma sağlamak için iş parçacığı yerel depolama Windows tanıtıcı eşlemeleri geçici ve kalıcı tutulur çünkü. İş parçacığı gibi olamaz ve bir hesaplama gerçekleştirmek sonra belgenin çağrı `UpdateAllViews` değiştiren yeni verilerin görünümlerini içeren windows için üye işlevi. Bu, çünkü etkisizdir eşlemesinden `CWnd` Cwnd'lerden için nesneleri, birincil iş parçacığına yerel. Bu, tek bir iş parçacığı bir C++ nesnesi için bir Windows tanıtıcı eşlemeyi olabilir, ancak başka bir iş parçacığı için farklı bir C++ nesnesi aynı tanıtıcıyı eşleyebilir anlamına gelir. Bir iş parçacığında yapılan değişiklikler diğer yansıtılmaz.

Bu sorunu gidermek için birkaç yol vardır. İlk tek tek işler (örneğin, bir HWND) çalışan iş parçacığı C++ nesneleri yerine geçirmektir. Çalışan iş parçacığı ardından bu nesneleri geçici eşlemesine uygun çağırarak ekler `FromHandle` üye işlevi. Çağırarak iş parçacığının kalıcı haritaya nesne ekleyebilirsiniz `Attach`, ancak yalnızca nesne iş parçacığı artık mevcut garanti edilir, bunun yapılması gerekir.

Farklı görevler, çalışan iş parçacıkları gerçekleştirme ve uygulamanın ana pencere için bu ileti göndermek için karşılık gelen yeni kullanıcı tanımlı iletileri oluşturmak için başka bir yöntemdir kullanarak `::PostMessage`. Bu yöntem iletişim dışında her iki iş parçacığı aynı adres alanında yürütülen konuşmaya iki farklı uygulamalara benzerdir.

Tanıtıcı eşlemeleri hakkında daha fazla bilgi için bkz. [Teknik Not 3](../mfc/tn003-mapping-of-windows-handles-to-objects.md). İş parçacığı yerel depolama hakkında daha fazla bilgi için bkz. [iş parçacığında yerel depolama](/windows/desktop/ProcThread/thread-local-storage) ve [kullanarak iş parçacığı yerel depolama](/windows/desktop/ProcThread/using-thread-local-storage) Windows SDK.

##  <a name="_core_communicating_between_threads"></a> İş parçacıkları arasında iletişim kurma

MFC, birkaç iş parçacığı güvenliği sağlamak için nesnelere erişimi eşitlemek için iş parçacığı izin sınıflar sağlar. Bu sınıfların kullanımı, açıklanan [çoklu iş parçacığı kullanımı: Eşitleme sınıflarının nasıl kullanılacağını](multithreading-how-to-use-the-synchronization-classes.md) ve [çoklu iş parçacığı kullanımı: Zaman eşitleme sınıflarını kullanma](multithreading-when-to-use-the-synchronization-classes.md). Bu nesneler hakkında daha fazla bilgi için bkz: [eşitleme](/windows/desktop/Sync/synchronization) Windows SDK.

## <a name="see-also"></a>Ayrıca bkz.

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)
