---
description: 'Hakkında daha fazla bilgi edinin: Eşzamanlılık Çalışma Zamanı diğer eşzamanlılık modelleriyle karşılaştırma'
title: Eşzamanlılık Çalışma Zamanını Diğer Eşzamanlılık Modelleriyle Karşılaştırma
ms.date: 11/04/2016
helpviewer_keywords:
- Concurrency Runtime, compared to other models
ms.assetid: d8b9a1f4-f15f-43c3-a5b4-c0991edf9c86
ms.openlocfilehash: 3259d24d4eb3d5b4af9731b97c343d4dd01ea6e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271491"
---
# <a name="comparing-the-concurrency-runtime-to-other-concurrency-models"></a>Eşzamanlılık Çalışma Zamanını Diğer Eşzamanlılık Modelleriyle Karşılaştırma

Bu belgede Eşzamanlılık Çalışma Zamanı ve diğer teknolojilerin Özellikler ve programlama modelleri arasındaki farklar açıklanmaktadır. Eşzamanlılık Çalışma Zamanı avantajlarının diğer programlama modellerinin avantajları ile nasıl karşılaştırılacağını anlamak için, uygulamalarınızın gereksinimlerini en iyi şekilde karşılayan teknolojiyi seçebilirsiniz.

Şu anda Windows iş parçacığı havuzu veya OpenMP gibi başka bir programlama modeli kullanıyorsanız, Eşzamanlılık Çalışma Zamanı geçiş için uygun olabilecek durumlar vardır. Örneğin, [OpenMP 'dan eşzamanlılık çalışma zamanı geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md) konusu, openmp 'dan eşzamanlılık çalışma zamanı geçirmeye ne zaman uygun olduğunu anlatmaktadır. Ancak, uygulama performansı ve geçerli hata ayıklama desteğiyle memnun kaldıysanız geçiş gerekli değildir.

Başka bir eşzamanlılık modeli kullanan mevcut uygulamanızı tamamlamak için Eşzamanlılık Çalışma Zamanı özellikleri ve verimlilik avantajlarından yararlanabilirsiniz. Eşzamanlılık Çalışma Zamanı, birden çok görev zamanlayıcılar aynı bilgi işlem kaynakları için rekabet edildiğinde yük dengelemeyi garanti edemez. Ancak, iş yükleri çakışmazsa, bu efekt en düşük düzeydedir.

## <a name="sections"></a><a name="top"></a> Başlıklı

- [Preemptive zamanlamasını birlikte çalışır zamanlamaya göre karşılaştırma](#models)

- [Eşzamanlılık Çalışma Zamanı Windows API 'siyle karşılaştırma](#winapi)

- [Eşzamanlılık Çalışma Zamanı OpenMP ile karşılaştırma](#openmp)

## <a name="comparing-preemptive-scheduling-to-cooperative-scheduling"></a><a name="models"></a> Preemptive zamanlamasını birlikte çalışır zamanlamaya göre karşılaştırma

Preemptive modeli ve birlikte çalışırken zamanlama modelleri, işlem kaynaklarını paylaşmak için birden çok görevi etkinleştirmenin iki yaygın yollarıdır. Örneğin, işlemciler veya donanım iş parçacıkları.

### <a name="preemptive-and-cooperative-scheduling"></a>PreEmptive ve Cooperative zamanlaması

*Preemptive zamanlama* , her görevin belirli bir süre için bir bilgi işlem kaynağına özel erişim izni veren ve daha sonra başka bir göreve geçiş yapan, hepsini bir kez deneme, önceliğe dayalı bir mekanizmadır. Preemptive zamanlama, Windows gibi çok görevli işletim sistemlerinde ortaktır. *Ortak zamanlama* , görev bitene veya görev kaynağa erişimi yapana kadar, her görevin bir bilgi işlem kaynağına özel olarak erişmesini sağlayan bir mekanizmadır. Eşzamanlılık Çalışma Zamanı, işlem kaynaklarının en yüksek kullanımını sağlamak için işletim sisteminin preemptive Scheduler ile birlikte birlikte çalışan zamanlamayı kullanır.

### <a name="differences-between-preemptive-and-cooperative-schedulers"></a>PreEmptive ve Cooperative zamanlayıcılar arasındaki farklar

Her iş parçacığının devam ettiğinden emin olmak için birden çok iş parçacığını, bilgi işlem kaynaklarına erişim izni vermek için preemptive zamanlayıcılar arama. Birçok bilgi işlem kaynağına sahip bilgisayarlarda, dengeli erişim sağlamak daha az sorunlu olur; Ancak, kaynakların etkin kullanımının daha fazla soruna neden olma.

Bir preemptive çekirdek modu Zamanlayıcı, uygulama kodunun zamanlama kararları vermek için işletim sistemine dayanmasını gerektirir. Buna karşılık, Kullanıcı modu bir örnek Zamanlayıcı, uygulama kodunun kendi zamanlama kararlarını yapmasını sağlar. Ortak zamanlama, uygulama tarafından birçok zamanlama kararı sağladığından, çekirdek modu eşitlemeyle ilişkili ek yükün çoğunu azaltır. Ortak bir Zamanlayıcı genellikle zamanlamaya yönelik başka bir iş olmadığında, işletim sistemi çekirdeğine kararlar vermez. Aynı zamanda, çekirdeğe iletilen bir engelleme işlemi olduğunda, ancak bu işlem Kullanıcı modu zamanlayıcısına iletilmeyen bir zamanlayıcı, aynı zamanda işletim sistemi zamanlayıcısına de erteler.

### <a name="cooperative-scheduling-and-efficiency"></a>İşbirliksel zamanlama ve verimlilik

Bir preemptive Scheduler 'da, aynı öncelik düzeyine sahip olan tüm işler eşittir. Bir preemptive Zamanlayıcı genellikle iş parçacıklarını oluşturuldukları sırada zamanlar. Ayrıca, bir preemptive Zamanlayıcı, iş parçacığı önceliğine göre her iş parçacığını her bir zaman dilimi olarak bir zaman dilimine sahip olacak şekilde verir. Bu mekanizma eşitliği sağlar (her iş parçacığı ileri ilerleme durumu oluşturur), bu, verimlilik açısından biraz daha gelir. Örneğin, birçok hesaplama yoğunluklu algoritma eşitliği gerektirmez. Bunun yerine, ilgili görevlerin en az genel sürede sona ermesi önemlidir. Ortak zamanlama, uygulamanın daha verimli bir şekilde çalışmasını sağlar. Örneğin, çok sayıda iş parçacığı olan bir uygulamayı düşünün. Aynı anda çalıştırılacak kaynakları paylaşmayan zamanlama iş parçacıkları, eşitleme yükünü azaltabilir ve böylece verimliliği artırabilir. Görevleri zamanlamaya yönelik başka bir yöntem de, her bir ardışık düzen aşamasının daha önce bellek önbelleğine yüklenmiş olması için, görevlerin işlem hatlarını (her görevin bir önceki birinin çıktısı üzerinde hareket ettiği yer) çalıştırması.

### <a name="using-preemptive-and-cooperative-scheduling-together"></a>PreEmptive ve Cooperative zamanlamasını birlikte kullanma

Ortak zamanlama, tüm zamanlama sorunlarını çözmez. Örneğin, diğer görevlere oldukça bir şekilde davranmayan görevler, kullanılabilir tüm bilgi işlem kaynaklarını kullanabilir ve diğer görevlerin ilerleme yapmasını önler. Eşzamanlılık Çalışma Zamanı, preemptive Scheduling 'in eşitliği garantilerini tamamlamak için birlikte kullanılan iş çizelgelemenin verimlilik avantajlarını kullanır. Varsayılan olarak Eşzamanlılık Çalışma Zamanı, işlem kaynakları arasında çalışmayı verimli bir şekilde dağıtmak için bir iş hırsızlığı algoritması kullanan bir ortak Zamanlayıcı sağlar. Ancak Eşzamanlılık Çalışma Zamanı Zamanlayıcı, kaynakları uygulamalar arasında oldukça dağıtmak için işletim sisteminin preemptive Scheduler ' u de kullanır. Ayrıca, iş parçacığı yürütmesi üzerinde ayrıntılı denetim oluşturmak için uygulamalarınızda özel zamanlayıcılar ve Zamanlayıcı ilkeleri de oluşturabilirsiniz.

[[Üst](#top)]

## <a name="comparing-the-concurrency-runtime-to-the-windows-api"></a><a name="winapi"></a> Eşzamanlılık Çalışma Zamanı Windows API 'siyle karşılaştırma

Genellikle Windows API (ve daha önce Win32 olarak bilinirdi) olarak adlandırılan Microsoft Windows uygulama programlama arabirimi, uygulamalarınızda eşzamanlılık sağlayan bir programlama modeli sağlar. Eşzamanlılık Çalışma Zamanı, temel işletim sisteminden kullanılamayan ek programlama modelleri sağlamak için Windows API üzerinde oluşturulur.

Eşzamanlılık Çalışma Zamanı paralel çalışma gerçekleştirmek için Windows API iş parçacığı modelinde oluşturulur. Ayrıca Windows API bellek yönetimi ve iş parçacığı yerel depolama mekanizmalarını kullanır. Windows 7 ve Windows Server 2008 R2 'de, Kullanıcı-zamanlanabilen iş parçacıkları ve 64 ' den fazla donanım iş parçacığına sahip bilgisayarlar için Windows API desteği kullanır. Eşzamanlılık Çalışma Zamanı, bilgi işlem kaynaklarının kullanımını en üst düzeye çıkarmak ve birden çok eş zamanlı zamanlayıcı örneğini etkinleştirerek bir iş hırsızlığı algoritması sağlayarak Windows API modelini genişletir.

### <a name="programming-languages"></a>Programlama Dilleri

Windows API, programlama modelini göstermek için C programlama dilini kullanır. Eşzamanlılık Çalışma Zamanı, C++ dilinde en yeni özelliklerden yararlanan bir C++ programlama arabirimi sağlar. Örneğin, Lambda işlevleri paralel çalışma işlevlerini tanımlamak için kısa, tür açısından güvenli bir mekanizma sağlar. Eşzamanlılık Çalışma Zamanı kullandığı en yeni C++ özellikleri hakkında daha fazla bilgi için bkz. [genel bakış](../../parallel/concrt/asynchronous-message-blocks.md).

### <a name="threads-and-thread-pools"></a>İş parçacıkları ve Iş parçacığı havuzları

Windows API 'sindeki merkezi eşzamanlılık mekanizması iş parçacığıdır. Genellikle iş parçacığı oluşturmak için [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) işlevini kullanırsınız. İş parçacıklarının oluşturulması ve kullanılması görece kolay olsa da, işletim sistemi bunları yönetmek için önemli miktarda süre ve diğer kaynakları ayırır. Buna ek olarak, her iş parçacığının aynı çalışma zamanını aynı öncelik düzeyinde alması garanti edilse de, ilişkili ek yük, yeterince büyük görevler oluşturmanızı gerektirir. Daha küçük veya daha ayrıntılı görevler için, eşzamanlılık ile ilişkili ek yük, görevleri paralel olarak çalıştırmanın avantajını engelleyebilir.

İş parçacığı havuzları, iş parçacığı yönetiminin maliyetini azaltmanın bir yoludur. Windows API tarafından sunulan özel iş parçacığı havuzları ve iş parçacığı havuzu uygulamasının her ikisi de küçük çalışma öğelerini paralel olarak verimli bir şekilde çalışacak şekilde etkinleştirir. Windows iş parçacığı havuzu, iş öğelerini ilk ın, ilk çıkar (FıFO) kuyruğunda tutar. Her iş öğesi havuza eklendiği sırayla başlatılır.

Eşzamanlılık Çalışma Zamanı, FıFO zamanlama mekanizmasını genişletmek için bir iş hırsızlığı algoritması uygular. Algoritma, henüz başlatılmamış görevleri iş öğelerinin dışında çalışan iş parçacıklarına taşımıyor. İş hırsızlığı algoritması iş yüklerini dengeleyebilir, ancak iş öğelerinin yeniden düzenlenmesine da neden olabilir. Bu yeniden sıralama işlemi, bir iş öğesinin gönderildiğinden farklı bir sırayla başlatılmasına neden olabilir. Bu, verilerin daha yeni görevler arasında daha eski olanlar arasından paylaşıldığından daha iyi bir şansınız olan özyinelemeli algoritmalarda yararlıdır. İlk önce çalıştırılacak yeni öğeleri almak, daha az önbellek isabetsizlik ve muhtemelen daha az sayfa hatası anlamına gelir.

İşletim sisteminin perspektifinden, iş hırsızlığı dengeli değildir. Ancak, bir uygulama bir algoritma veya görevi paralel olarak çalışacak şekilde uygularsa, alt görevler arasında eşitliği her zaman bir önemi yoktur. Genel görevin ne kadar hızlı bir şekilde bitdiğine göre. Diğer algoritmalar için, FıFO uygun zamanlama stratejisidir.

### <a name="behavior-on-various-operating-systems"></a>Çeşitli Işletim sistemlerinde davranış

Windows XP ve Windows Vista 'da, Windows Vista 'da yığın performansı iyileştirildiğinden, Eşzamanlılık Çalışma Zamanı kullanan uygulamalar benzer şekilde davranır.

Windows 7 ve Windows Server 2008 R2 'de, işletim sistemi Eşzamanlılık ve ölçeklenebilirliği daha da destekler. Örneğin, bu işletim sistemleri 64 ' den fazla donanım iş parçacığına sahip bilgisayarları destekler. Bu yeni özelliklerden faydalanmak için Windows API kullanan mevcut bir uygulamanın değiştirilmesi gerekir. Ancak, Eşzamanlılık Çalışma Zamanı kullanan bir uygulama otomatik olarak bu özellikleri kullanır ve değişiklik gerektirmez.

[temel. Kullanıcı-mode_scheduling](/windows/win32/procthread/user-mode-scheduling)

[[Üst](#top)]

## <a name="comparing-the-concurrency-runtime-to-openmp"></a><a name="openmp"></a> Eşzamanlılık Çalışma Zamanı OpenMP ile karşılaştırma

Eşzamanlılık Çalışma Zamanı çeşitli programlama modellerine izin vermez. Bu modeller diğer kitaplıkların modellerini örtüşebilir veya tamamlayabilir. Bu bölüm Eşzamanlılık Çalışma Zamanı [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp)ile karşılaştırır.

OpenMP programlama modeli açık bir standart tarafından tanımlanır ve FORTRAN ve C/C++ programlama dillerinin iyi tanımlanmış bağlamaları vardır. OpenMP 2,0 ve 2,5 sürümleri, yinelemeli bir paralel algoritmalarda iyi uygundur; diğer bir deyişle, bir dizi veri üzerinde paralel yineleme gerçekleştirir. Paralellik derecesi önceden belirleniyorsa ve sistemdeki kullanılabilir kaynaklarla eşleşiyorsa OpenMP en verimli yöntemdir. OpenMP modeli, çok büyük hesaplama sorunlarının tek bir bilgisayarın işleme kaynaklarında dağıtıldığı yüksek performanslı bilgi işlem için özellikle iyi bir eşleşmedir. Bu senaryoda, donanım ortamı bilinirdi ve geliştirici, algoritma yürütüldüğünde işlem kaynaklarına özel erişime sahip olmasını makul bir şekilde bekleyebilir.

Ancak, diğer, daha az kısıtlanmış bilgi işlem ortamları OpenMP için iyi bir eşleşmeyebilir. Örneğin, özyinelemeli sorunlar (Hızlı sıralama algoritması veya bir veri ağacını arama gibi), OpenMP kullanarak uygulanması daha zordur. Eşzamanlılık Çalışma Zamanı, [paralel Desenler kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (ppl) ve [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)sağlayarak OpenMP özelliklerini tamamlar. OpenMP 'den farklı olarak Eşzamanlılık Çalışma Zamanı, kullanılabilir kaynaklara uyum sağlayan dinamik bir Zamanlayıcı sağlar ve iş yükleri değiştiğinde paralellik derecesini ayarlar.

Eşzamanlılık Çalışma Zamanı özelliklerin birçoğu genişletilebilir. Ayrıca, yeni yenilerini oluşturmak için var olan özellikleri birleştirebilirsiniz. OpenMP derleyici yönergelerini kullandığından, kolayca genişletilemez.

Eşzamanlılık Çalışma Zamanı OpenMP ile nasıl Karşılaştırıldığı ve mevcut OpenMP kodunun Eşzamanlılık Çalışma Zamanı kullanmak için nasıl geçirileceğiyle ilgili daha fazla bilgi için, bkz. [OpenMP 'den eşzamanlılık çalışma zamanı 'e geçme](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md).

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)<br/>
[Genel Bakış](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp)
