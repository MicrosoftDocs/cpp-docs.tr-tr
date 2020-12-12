---
description: 'Hakkında daha fazla bilgi edinin: C ve Win32 ile çoklu Iş parçacığı'
title: C ve Win32 ile Çoklu İş Parçacığı Kullanımı
ms.date: 08/09/2019
helpviewer_keywords:
- Windows API [C++], multithreading
- multithreading [C++], C and Win32
- Visual C, multithreading
- Win32 applications [C++], multithreading
- threading [C++], C and Win32
- Win32 [C++], multithreading
- threading [C]
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
ms.openlocfilehash: cde6166f071035edd4aa0a07f578c6e3b66a0c21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149831"
---
# <a name="multithreading-with-c-and-win32"></a>C ve Win32 ile Çoklu İş Parçacığı Kullanımı

Microsoft C/C++ derleyicisi (MSVC), çoklu iş parçacıklı uygulamalar oluşturmaya yönelik destek sağlar. Uygulamanızın, Kullanıcı arabiriminin yanıt vermemeye başlamasına neden olacak pahalı işlemler gerçekleştirmesi gerekiyorsa, birden fazla iş parçacığı kullanmayı düşünün.

MSVC ile birden çok iş parçacığı ile programlama için birkaç yol vardır: C++/Wınrt ve Windows Çalışma Zamanı Kitaplığı, Microsoft Foundation Class (MFC) kitaplığı, C++/CLı ve .NET çalışma zamanını ya da C çalışma zamanı kitaplığını ve Win32 API kullanabilirsiniz. Bu makale, C 'de çoklu iş parçacığı oluşturma ile ilgilidir. Örnek kod için bkz. [C 'de örnek çoklu iş parçacığı programı](sample-multithread-c-program.md).

## <a name="multithread-programs"></a>Çoklu iş parçacığı kullanan programlar

Bir iş parçacığı temelde bir program aracılığıyla yürütme yoludur. Ayrıca, Win32 zamanlamalarının en küçük yürütme birimidir. Bir iş parçacığı, bir yığından, CPU yazmaçlarının durumuyla ve sistem Scheduler 'ın yürütme listesindeki bir girişin oluşur. Her bir iş parçacığı tüm işlem kaynaklarını paylaşır.

Bir işlem, bir veya daha fazla iş parçacığından ve bellekteki bir programın kod, veri ve diğer kaynaklarından oluşur. Tipik program kaynakları, açık dosyalar, Semaforlar ve dinamik olarak ayrılmış bellektir. Bir program, sistem Zamanlayıcı iş parçacıklarının yürütme denetiminden birine neden olduğunda yürütülür. Zamanlayıcı hangi iş parçacıklarının çalışacağını ve ne zaman çalışacağını belirler. Daha yüksek öncelikli iş parçacıklarının görevlerini tamamlarken daha düşük öncelikli iş parçacıkları beklemeniz gerekebilir. Çok işlemcili makinelerde Zamanlayıcı, CPU yükünü dengelemek için bireysel iş parçacıklarını farklı işlemcilere taşıyabilir.

İşlemdeki her iş parçacığı bağımsız olarak çalışır. Bunları birbirlerine görünür hale yapmadığınız sürece, iş parçacıkları tek tek yürütülür ve bir işlemdeki diğer iş parçacıklarını farkında değildir. Bununla birlikte ortak kaynakları paylaşan iş parçacıkları, semaforlarını veya başka bir ara işlem iletişim yöntemini kullanarak çalışmalarını koordine etmelidir. İş parçacıklarını eşitleme hakkında daha fazla bilgi için bkz. çok [Iş parçacıklı Win32 programı yazma](#writing-a-multithreaded-win32-program).

## <a name="library-support-for-multithreading"></a>Çoklu iş parçacığı kullanımı için kitaplık desteği

Artık CRT 'nin tüm sürümleri, bazı işlevlerin kilitleme dışı sürümleri dışında çoklu iş parçacığı oluşturmayı desteklemektedir. Daha fazla bilgi için bkz. çok [Iş parçacıklı kitaplıklar performansı](../c-runtime-library/multithreaded-libraries-performance.md). Kodunuzla bağlantı için kullanılabilen CRT sürümleri hakkında bilgi için bkz. [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md).

## <a name="include-files-for-multithreading"></a>Çoklu iş parçacığı kullanımı için dosyaları ekleme

Standart CRT içerme dosyaları, kitaplıklarda uygulanan şekilde C çalışma zamanı kitaplık işlevlerini bildirir. Derleyici seçenekleriniz [__fastcall veya __vectorcall](../build/reference/gd-gr-gv-gz-calling-convention.md) çağırma kurallarını belirtiyorsa, derleyici tüm işlevlerin yazmaç çağırma kuralını kullanarak çağrılması gerektiğini varsayar. Çalışma zamanı kitaplığı işlevleri C çağırma kuralını kullanır ve standart içerme dosyalarındaki bildirimler derleyiciye bu işlevlere doğru dış başvurular oluşturmasını söyler.

## <a name="crt-functions-for-thread-control"></a>İş parçacığı denetimi için CRT işlevleri

Tüm Win32 programlarında en az bir iş parçacığı vardır. Herhangi bir iş parçacığı, ek iş parçacıkları oluşturabilir. Bir iş parçacığı, işini hızlı bir şekilde tamamlayabilir ve sonra sonlandırabilir veya programın ömrü boyunca etkin kalabilirler.

CRT kitaplıkları, iş parçacığı oluşturma ve sonlandırma için aşağıdaki işlevleri sağlar: [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md), [_endthread ve _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md).

`_beginthread`Ve `_beginthreadex` işlevleri yeni bir iş parçacığı oluşturur ve işlem başarılı olursa bir iş parçacığı tanımlayıcı döndürür. Yürütme tamamlandığında iş parçacığı otomatik olarak sonlandırılır. Ya da, veya öğesine yapılan çağrısıyla kendisini sonlandırabilir `_endthread` `_endthreadex` .

> [!NOTE]
> Libcmt. lib ile oluşturulmuş bir programdan C çalışma zamanı yordamlarını çağırırsanız, iş parçacıklarını `_beginthread` or işleviyle başlatmanız gerekir `_beginthreadex` . Win32 işlevlerini `ExitThread` ve kullanın `CreateThread` . Kullanımı, `SuspendThread` askıya alınan iş parçacığının C çalışma zamanı veri yapısına erişimini tamamlaması beklenirken birden fazla iş parçacığı engellendiğinde kilitlenmeyle sonuçlanabilir.

### <a name="the-_beginthread-and-_beginthreadex-functions"></a><a name="_core_the__beginthread_function"></a> _Beginthread ve _beginthreadex işlevleri

`_beginthread`Ve `_beginthreadex` işlevleri yeni bir iş parçacığı oluşturur. Bir iş parçacığı, bir işlemin kod ve veri segmentlerini işlemdeki diğer iş parçacıklarıyla paylaşır, ancak kendi benzersiz yazmaç değerleri, yığın alanı ve geçerli yönerge adresine sahiptir. Sistem her iş parçacığına CPU süresi verir, böylece bir işlemdeki tüm iş parçacıkları eşzamanlı olarak çalıştırılabilir.

`_beginthread` ve `_beginthreadex` Win32 API [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) işlevine benzerdir, ancak bu farklılıklara sahiptir:

- Belirli C çalışma zamanı kitaplık değişkenlerini başlatır. Bu, yalnızca iş parçacıklarında C çalışma zamanı kitaplığını kullanıyorsanız önemlidir.

- `CreateThread` Güvenlik öznitelikleri üzerinde denetim sağlanmasına yardımcı olur. Bu işlevi, askıya alınmış durumda bir iş parçacığı başlatmak için kullanabilirsiniz.

`_beginthread` ve `_beginthreadex` başarılı olursa yeni iş parçacığına bir tanıtıcı veya hata varsa hata kodu döndürür.

### <a name="the-_endthread-and-_endthreadex-functions"></a><a name="_core_the__endthread_function"></a> _Endthread ve _endthreadex işlevleri

[_Endthread](../c-runtime-library/reference/endthread-endthreadex.md) işlevi tarafından oluşturulan bir iş parçacığını sonlandırır `_beginthread` (ve benzer şekilde, `_endthreadex` tarafından oluşturulan bir iş parçacığını sonlandırır `_beginthreadex` ). İş parçacıkları tamamlandığında otomatik olarak sonlandırılır. `_endthread` ve `_endthreadex` bir iş parçacığı içinden koşullu sonlandırma için faydalıdır. İletişim bağlantı noktasının denetimini alamazsanız, örneğin, iletişim işlemeye adanmış bir iş parçacığı çıkabilir.

## <a name="writing-a-multithreaded-win32-program"></a>Çoklu iş parçacığı kullanan Win32 programı yazma

Birden çok iş parçacığı içeren bir program yazdığınızda, bunların davranışlarını ve [Program kaynaklarının kullanımını](#_core_sharing_common_resources_between_threads)koordine etmeniz gerekir. Ayrıca, her bir iş parçacığının [kendi yığınını](#_core_thread_stacks)aldığından emin olun.

### <a name="sharing-common-resources-between-threads"></a><a name="_core_sharing_common_resources_between_threads"></a> İş parçacıkları arasında ortak kaynakları paylaşma

> [!NOTE]
> MFC bakış noktasından benzer bir tartışma için bkz. [Çoklu Iş parçacığı kullanımı: programlama ipuçları](multithreading-programming-tips.md) ve [Çoklu iş parçacığı oluşturma: eşitleme sınıfları ne zaman kullanılır](multithreading-when-to-use-the-synchronization-classes.md)?.

Her iş parçacığının kendi yığını ve kendi CPU yazmaçlarının kopyası vardır. Dosyalar, statik veriler ve yığın bellek gibi diğer kaynaklar, işlemdeki tüm iş parçacıkları tarafından paylaşılır. Bu ortak kaynakları kullanan iş parçacıkları eşitlenmelidir. Win32, Semaforlar, kritik bölümler, olaylar ve zaman uyumu sağlayıcılar dahil olmak üzere kaynakları eşitlemeye yönelik çeşitli yollar sağlar.

Birden çok iş parçacığı statik verilere erişirken, programınızın olası kaynak çakışmalarını sağlaması gerekir. Bir iş parçacığının başka bir iş parçacığı tarafından görüntülenmek üzere *x*,*y* koordinatları içeren bir statik veri yapısını güncelleştirdiği bir programı düşünün. Güncelleştirme iş parçacığı *x* koordinatını değiştirirse ve *y* koordinatını değiştirebilmek için önce önayarlanırsa, *y* koordinatı güncellenmek için görüntü iş parçacığı zamanlanabilir. Öğe yanlış konumda görüntülenir. Yapıya erişimi denetlemek için semaforları kullanarak bu sorundan kaçınabilirsiniz.

Bir mutex *(örneğin,* stand için kısa bir süre), bir diğerinden zaman uyumsuz olarak yürütülen iş parçacıkları veya süreçler arasında iletişim kurma yöntemidir. Bu iletişim, genellikle kaynağı kilitleyerek ve kilidini açarak, paylaşılan bir kaynağa erişimi denetleyerek birden çok iş parçacığının veya işlemin etkinliklerini koordine etmek için kullanılabilir. Bu *x*,*y* koordinatı güncelleştirme sorununu çözmek için, güncelleştirme iş parçacığı, güncelleştirme gerçekleştirilmeden önce veri yapısının kullanımda olduğunu gösteren bir mutex ayarlar. Her iki koordinat işlendikten sonra mutex 'i temizler. Görüntüleme iş parçacığı, görüntüyü güncelleştirmeden önce mutex 'in temiz olmasını beklemelidir. Bu işlem için bekleyen bu işleme, işlem engellendiği ve mutex temizlenene kadar devam edemediği için bir mutex üzerinde *engelleme* olarak adlandırılır.

[Örnek çoklu Iş parçacığı c programında](sample-multithread-c-program.md) gösterilen sıçrama. c programı, `ScreenMutex` ekran güncelleştirmelerini koordine etmek için adlı bir mutex kullanır. Görüntüleme iş parçacıklarından birinin ekrana yazmaya hazır olduğu her seferinde, `WaitForSingleObject` `ScreenMutex` `WaitForSingleObject` çağrının mutex üzerinde engellenmesi ve zaman aşımına uğrar olması gerektiğini göstermek için tanıtıcı ve sabit sonsuz ile çağrı yapılır. `ScreenMutex` Açık ise, bekleme işlevi mutex 'i diğer iş parçacıklarının görüntülemeyi kesintiye uğramaması için ayarlar ve iş parçacığını yürütmeye devam eder. Aksi takdirde, iş parçacığı mutex temizlenene kadar engeller. İş parçacığı görüntü güncelleştirmesini tamamladığında, öğesini çağırarak mutex 'i serbest bırakır `ReleaseMutex` .

Ekran görüntüleri ve statik veriler dikkatli yönetim gerektiren kaynaklardan yalnızca ikanıdır. Örneğin, programınız aynı dosyaya erişen birden fazla iş parçacığına sahip olabilir. Başka bir iş parçacığı dosya işaretçisini taşıabileceğinden, her iş parçacığının okumadan veya yazmadan önce dosya işaretçisini sıfırlaması gerekir. Ayrıca, her iş parçacığının, işaretçiyi konum ve dosyaya eriştiği zaman arasında yok olduğundan emin olması gerekir. Bu iş parçacıkları, `WaitForSingleObject` ve çağrılarıyla her bir dosya erişimini birleştirerek dosyaya erişimi koordine etmek için bir semafor kullanmalıdır `ReleaseMutex` . Aşağıdaki kod örneği bu tekniği göstermektedir:

```C
HANDLE    hIOMutex = CreateMutex (NULL, FALSE, NULL);

WaitForSingleObject( hIOMutex, INFINITE );
fseek( fp, desired_position, 0L );
fwrite( data, sizeof( data ), 1, fp );
ReleaseMutex( hIOMutex);
```

### <a name="thread-stacks"></a><a name="_core_thread_stacks"></a> İş parçacığı yığınları

Bir uygulamanın varsayılan yığın alanı, iş parçacığı 1 olarak bilinen yürütmenin ilk iş parçacığına ayrılır. Sonuç olarak, programınızın ihtiyaç duyacağı her ek iş parçacığı için ayrı bir yığın için ne kadar bellek ayrılacağını belirtmeniz gerekir. İşletim sistemi, gerekirse iş parçacığı için ek yığın alanı ayırır, ancak varsayılan bir değer belirtmeniz gerekir.

Çağrıdaki ilk bağımsız değişken, `_beginthread` `BounceProc` iş parçacıklarını yürüten işlevin bir işaretçisidir. İkinci bağımsız değişken, iş parçacığı için varsayılan yığın boyutunu belirtir. Son bağımsız değişken, öğesine geçirilen bir KIMLIK numarasıdır `BounceProc` . `BounceProc` Rastgele sayı oluşturucuyu temel almak ve iş parçacığının color özniteliğini ve görüntüleme karakterini belirlemek için KIMLIK numarasını kullanır.

C çalışma zamanı kitaplığı veya Win32 API çağrısı yapan iş parçacıkları, çağırdığı kitaplık ve API işlevleri için yeterli yığın alanına izin vermelidir. C `printf` işlevi, 500 bayttan daha fazla yığın alanı gerektirir ve Win32 API yordamlar çağrılırken, ek bir yığın alanı olan 2k bayt kullanılabilir olmalıdır.

Her iş parçacığının kendi yığınına sahip olduğu için, mümkün olduğunca az statik veri kullanarak veri öğeleri üzerinde potansiyel çakışmaları önleyebilirsiniz. Programınızı, bir iş parçacığına özel olabilecek tüm veriler için otomatik yığın değişkenlerini kullanacak şekilde tasarlayın. Sıçrama. c programındaki tek genel değişkenler, her zaman zaman uyumu veya başlatıldıktan sonra hiç değişmeme değişkenlerdir.

Win32 ayrıca iş parçacığı verilerini depolamak için Iş parçacığı yerel depolaması (TLS) sağlar. Daha fazla bilgi için bkz. [Iş parçacığı yerel depolaması (TLS)](thread-local-storage-tls.md).

## <a name="avoiding-problem-areas-with-multithread-programs"></a>Çoklu iş parçacığı kullanan programlarda sorun alanlarından kaçınma

Çoklu iş parçacıklı C programını oluştururken, bağlarken veya çalıştırırken karşılaşabileceğiniz birkaç sorun vardır. Daha yaygın sorunlardan bazıları aşağıdaki tabloda açıklanmıştır. (MFC görünüm noktasından benzer bir tartışma için bkz. [Çoklu Iş parçacığı kullanımı: programlama ipuçları](multithreading-programming-tips.md).)

|Sorun|Olası neden|
|-------------|--------------------|
|Programınızın bir koruma ihlaline neden olduğunu gösteren bir ileti kutusu alırsınız.|Birçok Win32 programlama hatası koruma ihlallerine neden olur. Koruma ihlallerinin yaygın bir nedeni, verilerin null işaretçilere dolaylı olarak atanmasından oluşur. Programınızın kendisine ait olmayan belleğe erişmeye çalıştığı için bir koruma ihlali verilir.<br /><br /> Bir koruma ihlalinin nedenini saptamanın kolay bir yolu, hata ayıklama bilgileri ile programınızı derleyip Visual Studio ortamındaki hata ayıklayıcı aracılığıyla çalıştırmayı kullanmaktır. Koruma hatası oluştuğunda, Windows denetimi hata ayıklayıcıya aktarır ve imleç soruna neden olan satıra yerleştirilir.|
|Programınız çok sayıda derleme ve bağlantı hatası oluşturuyor.|Derleyicinin uyarı düzeyini en yüksek değerlerden birine ayarlayarak ve uyarı iletilerini inceleyerek olası birçok sorunu ortadan kaldırabilirsiniz. Düzey 3 veya düzey 4 uyarı düzeyi seçeneklerini kullanarak, istemeyerek veri dönüştürmelerini, eksik işlev prototiplerini ve ANSI olmayan özelliklerin kullanımını tespit edebilirsiniz.|

## <a name="see-also"></a>Ayrıca bkz.

[Eski kod için çoklu iş parçacığı desteği (Visual C++)](multithreading-support-for-older-code-visual-cpp.md)\
[C 'de örnek çoklu iş parçacığı programı](sample-multithread-c-program.md)\
[İş parçacığı yerel depolaması (TLS)](thread-local-storage-tls.md)\
[C++/Wınrt ile eşzamanlılık ve zaman uyumsuz işlemler](/windows/uwp/cpp-and-winrt-apis/concurrency)\
[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)
