---
description: 'Daha fazla bilgi edinin: çoklu Iş parçacığı kullanımı: MFC programlama Ipuçları'
title: 'Çoklu iş parçacığı kullanımı: MFC programlama Ipuçları'
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
ms.openlocfilehash: 5c7141462da21c6b9298f48ab85b3de06a039d08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149896"
---
# <a name="multithreading-mfc-programming-tips"></a>Çoklu iş parçacığı kullanımı: MFC programlama Ipuçları

Çok iş parçacıklı uygulamalar, işlemlerin amaçlanan sırada gerçekleşmesini sağlamak için tek iş parçacıklı uygulamalardan daha sıkı bir şekilde ihtiyaç duyar ve birden fazla iş parçacığı tarafından erişilen tüm veriler bozuk değildir. Bu konuda, Microsoft Foundation Class (MFC) kitaplığıyla çok iş parçacıklı uygulamaları programlarken olası sorunları önleme teknikleri açıklanmaktadır.

- [Birden çok Iş parçacığından nesnelere erişme](#_core_accessing_objects_from_multiple_threads)

- [MFC nesneleri MFC olmayan Iş parçacıklarından erişme](#_core_accessing_mfc_objects_from_non.2d.mfc_threads)

- [Windows tanıtıcı eşlemeleri](#_core_windows_handle_maps)

- [Iş parçacıkları arasında iletişim kurma](#_core_communicating_between_threads)

## <a name="accessing-objects-from-multiple-threads"></a><a name="_core_accessing_objects_from_multiple_threads"></a> Birden çok Iş parçacığından nesnelere erişme

MFC nesneleri kendi kendine iş parçacığı güvenli değildir. MFC eşitleme sınıflarını ve/veya uygun Win32 eşitleme nesnelerini (örneğin, kritik bölümler) kullanmadığınız sürece iki ayrı iş parçacığı aynı nesneyi işleyebilir. Kritik bölümler ve diğer ilgili nesneler hakkında daha fazla bilgi için Windows SDK [eşitleme](/windows/win32/Sync/synchronization) konusuna bakın.

Sınıf kitaplığı, hata ayıklama belleği ayırma tarafından kullanılanlar gibi genel veri yapılarını korumak için önemli bölümleri dahili olarak kullanır.

## <a name="accessing-mfc-objects-from-non-mfc-threads"></a><a name="_core_accessing_mfc_objects_from_non.2d.mfc_threads"></a> MFC nesneleri MFC olmayan Iş parçacıklarından erişme

Bir iş parçacığını, bir [CWinThread](../mfc/reference/cwinthread-class.md) nesnesi kullanmaktan başka bir şekilde oluşturan çok iş parçacıklı bir uygulamanız varsa, o iş parçacığından diğer MFC nesnelerine erişemezsiniz. Diğer bir deyişle, ikincil bir iş parçacığından herhangi bir MFC nesnesine erişmek istiyorsanız, iş parçacığı oluşturma [: User-Interface Iş parçacıkları](multithreading-creating-user-interface-threads.md) veya çoklu iş parçacığı oluşturma [: çalışan iş parçacıkları oluşturma](multithreading-creating-worker-threads.md)bölümünde açıklanan yöntemlerden biriyle oluşturmanız gerekir. Bu yöntemler, sınıf kitaplığının çok iş parçacıklı uygulamaları işlemek için gerekli iç değişkenleri başlatmasını sağlayan tek alanlardır.

## <a name="windows-handle-maps"></a><a name="_core_windows_handle_maps"></a> Windows tanıtıcı eşlemeleri

Genel bir kural olarak, bir iş parçacığı yalnızca oluşturduğu MFC nesnelerine erişebilir. Bunun nedeni, geçici ve kalıcı Windows tanıtıcı eşlemelerinin, iş parçacığı yerel depolama alanında birden çok iş parçacığından eşzamanlı erişimlerden korunmasını sağlamaya yardımcı olur. Örneğin, bir çalışan iş parçacığı bir hesaplama gerçekleştiremez ve sonra, `UpdateAllViews` değiştirilen yeni verilerde görünümler içeren pencerelerin olması için bir belgenin üye işlevini çağırabilir. `CWnd`Nesnelerden HWND 'e olan eşleme birincil iş parçacığına yereldir çünkü bu, hiçbir etkiye sahip değildir. Bu, bir iş parçacığının bir Windows tanıtıcısından bir C++ nesnesine eşleme olabileceği, ancak başka bir iş parçacığının aynı tanıtıcıyı farklı bir C++ nesnesine eşleyebileceğiniz anlamına gelir. Bir iş parçacığında yapılan değişiklikler diğerine yansıtılmaz.

Bu sorunu çözmek için birkaç yol vardır. Birincisi, C++ nesneleri yerine, çalışan iş parçacığına her bir tutamacı (HWND gibi) geçirmektir. Ardından çalışan iş parçacığı, ilgili üye işlevini çağırarak bu nesneleri geçici eşlemesine ekler `FromHandle` . Ayrıca, öğesini çağırarak iş parçacığının kalıcı eşlemesine nesneyi ekleyebilirsiniz `Attach` , ancak bu, yalnızca nesnenin iş parçacığından daha uzun bir süre var olacağını garanti ediyorsanız yapılmalıdır.

Başka bir yöntem de çalışan iş parçacıklarından farklı görevlere karşılık gelen yeni kullanıcı tanımlı iletiler oluşturmaktır ve bu iletileri kullanarak uygulamanın ana penceresine nakleder `::PostMessage` . Bu iletişim yöntemi, her iki iş parçacığının de aynı adres alanında yürütülmesi dışında iki farklı uygulamaya benzer.

Tanıtıcı haritaları hakkında daha fazla bilgi için bkz. [teknik notta 3](../mfc/tn003-mapping-of-windows-handles-to-objects.md). İş parçacığı yerel depolama hakkında daha fazla bilgi için bkz. [Iş parçacığı yerel depolama](/windows/win32/ProcThread/thread-local-storage) ve Windows SDK [Iş parçacığı yerel depolama kullanma](/windows/win32/ProcThread/using-thread-local-storage) .

## <a name="communicating-between-threads"></a><a name="_core_communicating_between_threads"></a> Iş parçacıkları arasında iletişim kurma

MFC iş parçacıklarının iş parçacığı güvenliğini sürdürmek üzere nesnelere erişimi eşitlemesine izin veren bir dizi sınıf sağlar. Bu sınıfların kullanımı, [Çoklu Iş parçacığı kullanımı:](multithreading-how-to-use-the-synchronization-classes.md) eşitleme sınıfları ve [Çoklu iş parçacığı kullanımı: eşitleme sınıflarının ne zaman](multithreading-when-to-use-the-synchronization-classes.md)kullanılacağı açıklanmaktadır. Bu nesneler hakkında daha fazla bilgi için Windows SDK [eşitleme](/windows/win32/Sync/synchronization) konusuna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)
