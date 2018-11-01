---
title: Çoklu İş Parçacığı Kullanan Win32 Programı Yazma
ms.date: 11/04/2016
helpviewer_keywords:
- thread stacks [C++]
- resources [C++], multithreading
- stacks [C++]
- shared resources [C++]
- threading [C++], sharing common resources
- multithreading [C++], thread stacks
- multithreading [C++], sharing common resources
- mutual exclusion [C++]
- communications [C++], between threads
- mutex [C++]
- threading [C++], thread stacks
ms.assetid: 1415f47d-417f-4f42-949b-946fb28aab0e
ms.openlocfilehash: c7d9790cfee39fbddd9ab545d48fa375d56f3a05
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561336"
---
# <a name="writing-a-multithreaded-win32-program"></a>Çoklu İş Parçacığı Kullanan Win32 Programı Yazma

Birden çok iş parçacığı bir programla yazdığınızda, davranışları koordine ve [programın kaynaklarının kullanımını](#_core_sharing_common_resources_between_threads). Ayrıca her bir iş parçacığı aldığından emin olmak gerekir [kendi yığın](#_core_thread_stacks).

##  <a name="_core_sharing_common_resources_between_threads"></a> İş parçacıkları arasında ortak kaynakları paylaşma

> [!NOTE]
>  MFC açısından benzer bir tartışma için bkz: [çoklu iş parçacığı kullanımı: programlama ipuçları](multithreading-programming-tips.md) ve [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma zamanı](multithreading-when-to-use-the-synchronization-classes.md).

Her iş parçacığı kendi yığınını vardır ve kendi CPU kopyasını kaydeder. Dosyaları ve statik veri yığın bellek gibi diğer kaynaklar işlemdeki tüm iş parçacıkları tarafından paylaşılır. Bu ortak kaynakları kullanarak iş parçacıkları eşitlenmelidir. Win32 kaynakları semafor, kritik bölüm, olayları ve mutex'leri dahil olmak üzere, eşitleme için birçok yol sağlar.

Birden çok iş parçacığı statik verilere erişirken, programınız için olası kaynak çakışması sağlamanız gerekir. Bir iş parçacığı burada güncelleştirmeleri içeren bir statik veri yapısı bir program dikkate *x*,*y* başka bir iş parçacığı tarafından görüntülenecek öğeleri koordinatları. Güncelleştirme iş parçacığı değiştirirse *x* koordine etmek ve değiştirmeden önce etkisiz *y* koordinat, görüntü iş parçacığının önce zamanlanmış olabilmesidir *y* koordinatı güncelleştirildi. Yanlış konumunda öğe görüntülenir. Yapıya erişimi denetlemesi için semafor kullanarak bu sorunu önleyebilirsiniz.

Bir mutex (kısaltması *mut*ual *ex*clusion), iş parçacıkları veya başka birine zaman uyumsuz olarak yürütülen işlemler arasında iletişim kurulurken bir yoludur. Bu iletişim, genellikle paylaşılan bir kaynağa erişimi kilitleme ve kaynak kilidi denetleyerek etkinliklerini birden çok iş parçacıkları veya işlemlerdeki, genellikle koordine etmek için kullanılır. Bunu çözmek için *x*,*y* koordinat güncelleştirme sorunu güncelleştirme iş parçacığı veri yapısı güncelleştirmeyi uygulamadan önce kullanımda olduğunu belirten bir mutex ayarlar. Her iki koordinat işlendikten sonra bu mutex'i temizler. Görüntü iş parçacığının görünen güncelleştirmeden önce temizlenmesini mutex beklemelisiniz. Bekleyen bir mutex için bu işlemi, çoğunlukla işlem engellenir ve mutex temizlenene kadar devam edemez çünkü dışlamada engelleme adı verilir.

Bounce.c programın gösterilen [örnek çoklu iş parçacığı kullanan C programı](sample-multithread-c-program.md) adlandırılmış bir mutex kullanan `ScreenMutex` ekran güncelleştirmelerini koordine etmek için. Görüntü iş parçacıklarından ekrana yazmak için hazır olduğu her zaman çağırır `WaitForSingleObject` tanıtıcısını ile `ScreenMutex` ve göstermek için sabit SONSUZ `WaitForSingleObject` çağrı block mutex ve zaman aşımına uğramaz. Varsa `ScreenMutex` bekleme işlevi dışlamayı ayarlar, böylece görüntü ile diğer iş parçacıkları ve iş parçacığını yürütmeye devam ettirir. Mutex temizlenene kadar Aksi takdirde, iş parçacığını engeller. İş parçacığı görüntü güncelleştirme tamamlandığında çağırarak mutex serbest `ReleaseMutex`.

Ekran görüntüleri ve statik veriler yalnızca dikkatli yönetim gerektiren kaynaklara ikisidir. Örneğin, programınız aynı dosyaya erişen birden çok iş parçacığı sayısı olabilir. Dosya işaretçisini başka bir iş parçacığı taşınmış olduğundan, her iş parçacığı okuma veya yazma önce dosya işaretçisini sıfırlamanız gerekir. Ayrıca, her iş parçacığı, işaretçiyi vakit dosyasına erişir arasında etkisiz hale değil, emin olmanız gerekir. Bu iş parçacıkları ile her dosya erişimi köşeli ayraç kullanarak dosyaya erişim koordine etmek için semafor kullanmalısınız `WaitForSingleObject` ve `ReleaseMutex` çağırır. Aşağıdaki kod örneği, bu teknik gösterilmektedir:

```
HANDLE    hIOMutex= CreateMutex (NULL, FALSE, NULL);

WaitForSingleObject( hIOMutex, INFINITE );
fseek( fp, desired_position, 0L );
fwrite( data, sizeof( data ), 1, fp );
ReleaseMutex( hIOMutex);
```

##  <a name="_core_thread_stacks"></a> İş parçacığı yığınları

Bir uygulamanın varsayılan yığın alanı tümünün ilk iş parçacığında 1 iş parçacığı da bilinen, yürütme için ayrılır. Sonuç olarak, her ek iş parçacığı için ayrı bir yığın programınızı ayırmak için ne kadar bellek gerektiriyor belirtmeniz gerekir. Gerekirse ek yığın alanı işletim sistemi iş parçacığı için ayırır, ancak varsayılan bir değer belirtmeniz gerekir.

Birinci bağımsız değişkende `_beginthread` çağrıdır işaretçisi `BounceProc` iş parçacığını yürüten işlev. İkinci bağımsız değişkeni, iş parçacığı için varsayılan yığın boyutu belirtir. Son bağımsız değişken geçirilir bir kimlik numarasıdır `BounceProc`. `BounceProc` Rastgele sayı üreticisinin çekirdeğini ve iş parçacığının color özniteliği seçin ve karakter görüntülemek için kimlik numarasını kullanır.

C çalışma zamanı kitaplığı veya Win32 API çağrılarını iş parçacıkları, kitaplık ve bunlar çağrı API işlevleri için yeterli yığın alanı izin vermeniz gerekir. C `printf` işlevi, 500 bayttan daha fazla yığın alanı gerektirir ve kullanılabilir yığın alanı 2 K Win32 API yordamları ararken olması gerekir.

Her iş parçacığı kendi yığınını olduğundan, veri öğeleri üzerinde olası çakışmaları mümkün olduğunca az statik veri kullanarak önleyebilirsiniz. Programınızı otomatik yığın değişkenleri bir iş parçacığına özel tüm veriler için kullanılacak tasarlayın. Yalnızca genel Bounce.c programındaki mutex'leri ya da başlatıldıktan sonra hiçbir zaman değiştirme değişkenleri değişkenlerdir.

Win32 iş parçacığı yerel depolama (iş parçacığı başına verileri depolamak için TLS) de sağlar. Daha fazla bilgi için [iş parçacığı yerel depolaması (TLS)](thread-local-storage-tls.md).

## <a name="see-also"></a>Ayrıca Bkz.

[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](multithreading-with-c-and-win32.md)