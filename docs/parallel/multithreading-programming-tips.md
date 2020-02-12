---
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
ms.openlocfilehash: 79e7d440b478c759c5d4fd683d6af3423e7e8661
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140441"
---
# <a name="multithreading-mfc-programming-tips"></a>Çoklu iş parçacığı kullanımı: MFC programlama Ipuçları

Çok iş parçacıklı uygulamalar, işlemlerin amaçlanan sırada gerçekleşmesini sağlamak için tek iş parçacıklı uygulamalardan daha sıkı bir şekilde ihtiyaç duyar ve birden fazla iş parçacığı tarafından erişilen tüm veriler bozuk değildir. Bu konuda, Microsoft Foundation Class (MFC) kitaplığıyla çok iş parçacıklı uygulamaları programlarken olası sorunları önleme teknikleri açıklanmaktadır.

- [Birden çok Iş parçacığından nesnelere erişme](#_core_accessing_objects_from_multiple_threads)

- [MFC nesneleri MFC olmayan Iş parçacıklarından erişme](#_core_accessing_mfc_objects_from_non.2d.mfc_threads)

- [Windows tanıtıcı eşlemeleri](#_core_windows_handle_maps)

- [Iş parçacıkları arasında iletişim kurma](#_core_communicating_between_threads)

## <a name="_core_accessing_objects_from_multiple_threads"></a>Birden çok Iş parçacığından nesnelere erişme

MFC nesneleri kendi kendine iş parçacığı güvenli değildir. MFC eşitleme sınıflarını ve/veya uygun Win32 eşitleme nesnelerini (örneğin, kritik bölümler) kullanmadığınız sürece iki ayrı iş parçacığı aynı nesneyi işleyebilir. Kritik bölümler ve diğer ilgili nesneler hakkında daha fazla bilgi için Windows SDK [eşitleme](/windows/win32/Sync/synchronization) konusuna bakın.

Sınıf kitaplığı, hata ayıklama belleği ayırma tarafından kullanılanlar gibi genel veri yapılarını korumak için önemli bölümleri dahili olarak kullanır.

## <a name="_core_accessing_mfc_objects_from_non.2d.mfc_threads"></a>MFC nesneleri MFC olmayan Iş parçacıklarından erişme

Bir iş parçacığını, bir [CWinThread](../mfc/reference/cwinthread-class.md) nesnesi kullanmaktan başka bir şekilde oluşturan çok iş parçacıklı bir uygulamanız varsa, o iş parçacığından diğer MFC nesnelerine erişemezsiniz. Diğer bir deyişle, ikincil bir iş parçacığından herhangi bir MFC nesnesine erişmek istiyorsanız, bu iş parçacığını Çoklu iş parçacığı oluşturma [: Kullanıcı arabirimi Iş parçacıkları](multithreading-creating-user-interface-threads.md) veya [Çoklu iş parçacığı oluşturma: çalışan iş parçacıkları](multithreading-creating-worker-threads.md)oluşturma bölümünde açıklanan yöntemlerden biriyle oluşturmanız gerekir. Bu yöntemler, sınıf kitaplığının çok iş parçacıklı uygulamaları işlemek için gerekli iç değişkenleri başlatmasını sağlayan tek alanlardır.

## <a name="_core_windows_handle_maps"></a>Windows tanıtıcı eşlemeleri

Genel bir kural olarak, bir iş parçacığı yalnızca oluşturduğu MFC nesnelerine erişebilir. Bunun nedeni, geçici ve kalıcı Windows tanıtıcı eşlemelerinin, iş parçacığı yerel depolama alanında birden çok iş parçacığından eşzamanlı erişimlerden korunmasını sağlamaya yardımcı olur. Örneğin, bir çalışan iş parçacığı bir hesaplama gerçekleştiremez ve ardından bir belgenin `UpdateAllViews` üye işlevini çağırıp, değiştirilen yeni verilerde görünümler içeren pencereleri içerir. `CWnd` nesnelerinden HWNDs 'e olan eşleme birincil iş parçacığına yereldir çünkü bu, hiçbir etkiye sahip değildir. Bu, bir iş parçacığının bir Windows tanıtıcısından bir C++ nesneye eşleme olabileceği, ancak başka bir iş parçacığının aynı tanıtıcıyı farklı C++ bir nesneye eşleyebileceğiniz anlamına gelir. Bir iş parçacığında yapılan değişiklikler diğerine yansıtılmaz.

Bu sorunu çözmek için birkaç yol vardır. Birincisi, çalışan iş parçacığına C++ nesneler yerine bireysel TUTAMAÇLARı (HWND gibi) geçirmektir. Ardından çalışan iş parçacığı, uygun `FromHandle` üye işlevini çağırarak bu nesneleri geçici eşlemesine ekler. Ayrıca, `Attach`çağırarak iş parçacığının kalıcı eşlemesine nesneyi ekleyebilirsiniz, ancak bu, yalnızca nesnenin iş parçacığından daha uzun bir süre var olacağını garanti ediyorsanız yapılmalıdır.

Diğer bir yöntem, çalışan iş parçacıklarından farklı görevlere karşılık gelen yeni kullanıcı tanımlı iletiler oluşturmak ve `::PostMessage`kullanarak bu iletileri uygulamanın ana penceresine gönderkullanmaktır. Bu iletişim yöntemi, her iki iş parçacığının de aynı adres alanında yürütülmesi dışında iki farklı uygulamaya benzer.

Tanıtıcı haritaları hakkında daha fazla bilgi için bkz. [teknik notta 3](../mfc/tn003-mapping-of-windows-handles-to-objects.md). İş parçacığı yerel depolama hakkında daha fazla bilgi için bkz. [Iş parçacığı yerel depolama](/windows/win32/ProcThread/thread-local-storage) ve Windows SDK [Iş parçacığı yerel depolama kullanma](/windows/win32/ProcThread/using-thread-local-storage) .

## <a name="_core_communicating_between_threads"></a>Iş parçacıkları arasında iletişim kurma

MFC iş parçacıklarının iş parçacığı güvenliğini sürdürmek üzere nesnelere erişimi eşitlemesine izin veren bir dizi sınıf sağlar. Bu sınıfların kullanımı, [Çoklu Iş parçacığı kullanımı:](multithreading-how-to-use-the-synchronization-classes.md) eşitleme sınıfları ve [Çoklu iş parçacığı kullanımı: eşitleme sınıflarının ne zaman](multithreading-when-to-use-the-synchronization-classes.md)kullanılacağı açıklanmaktadır. Bu nesneler hakkında daha fazla bilgi için Windows SDK [eşitleme](/windows/win32/Sync/synchronization) konusuna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)
