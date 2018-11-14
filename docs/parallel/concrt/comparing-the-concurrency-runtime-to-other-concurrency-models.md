---
title: Eşzamanlılık Çalışma Zamanını Diğer Eşzamanlılık Modelleriyle Karşılaştırma
ms.date: 11/04/2016
helpviewer_keywords:
- Concurrency Runtime, compared to other models
ms.assetid: d8b9a1f4-f15f-43c3-a5b4-c0991edf9c86
ms.openlocfilehash: 82e1dca1345b909919320b911c4c107e965c9850
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51332679"
---
# <a name="comparing-the-concurrency-runtime-to-other-concurrency-models"></a>Eşzamanlılık Çalışma Zamanını Diğer Eşzamanlılık Modelleriyle Karşılaştırma

Bu belge özellikleri ve Eşzamanlılık Çalışma zamanı ve diğer teknolojilerden oluşan programlama modelleri arasındaki farkları açıklar. Nasıl eşzamanlılık çalışma zamanı avantajlarını diğer programlama modellerini kullanarak avantajlarını Karşılaştır anlayarak, uygulamalarınızın gereksinimlerini en iyi şekilde karşılayan teknolojisini seçebilirsiniz.

Şu anda, OpenMP ve Windows iş parçacığı havuzu gibi başka bir programlama modeli kullanıyorsanız burada eşzamanlılık çalışma zamanına geçirmek uygun olabilir durumlar vardır. Örneğin, konu [OpenMP döngüsünden eşzamanlılık çalışma zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md) zaman OpenMP döngüsünden eşzamanlılık çalışma zamanına geçirmek uygun olabilir açıklar. Ancak, uygulama performansı ve geçerli hata ayıklama desteği ile memnun kaldığınızda, geçiş gerekli değildir.

Başka bir tutarlılık modelini kullanan mevcut uygulamanızı tamamlamak için eşzamanlılık çalışma zamanı üretkenlik avantajları ve özellikleri kullanabilirsiniz. Eşzamanlılık Çalışma zamanı, aynı işlem kaynakları için birden çok görev planlayıcılar rekabet Yük Dengeleme garanti edemez. Ancak, iş yüklerini çakışmaması, bu etkiyi en alt düzeydedir.

##  <a name="top"></a> Bölümleri

- [İşbirlikçi planlama için PreEmptive planlama karşılaştırma](#models)

- [Eşzamanlılık Çalışma zamanı için Windows API ile karşılaştırma](#winapi)

- [Eşzamanlılık çalışma zamanını OpenMP karşılaştırma](#openmp)

##  <a name="models"></a> İşbirlikçi planlama için PreEmptive planlama karşılaştırma

Preemptive modeli ve modelleri zamanlama Guyana bilgi işlem kaynaklarını paylaşmak birden çok görevi etkinleştirmek için iki ortak işlemcileri veya donanım iş parçacıklarının yöntemleridir.

### <a name="preemptive-and-cooperative-scheduling"></a>PreEmptive ve işbirlikçi zamanlama

*PreEmptive zamanlama* her görev özel erişim, belirli bir süre için bir bilgi işlem kaynağına sağlar ve ardından başka bir göreve geçiş hepsini bir kez deneme, öncelik tabanlı bir mekanizma. PreEmptive zamanlama kullanılsın işletim sistemlerinde Windows gibi yaygın bir durumdur. *İşbirlikçi zamanlama* her görev özel erişim görev bitene kadar veya görev kaynak erişimini verir kadar bilgi işlem kaynak sağlayan bir mekanizmadır. Eşzamanlılık Çalışma zamanı, kaynakları işleme en fazla kullanım elde etmek için işletim sisteminin preemptive Zamanlayıcı ile birlikte işbirlikçi zamanlama kullanır.

### <a name="differences-between-preemptive-and-cooperative-schedulers"></a>Preemptive ve işbirlikçi zamanlayıcılar arasındaki farklar

Bulut bilgi işlem kaynakları, her iş parçacığı ilerleme aklınızdan sağlamak için birden çok iş parçacığı eşit şekilde erişmesini sağlamak PreEmptive zamanlayıcılar isteyin. Çok sayıda bilgi işlem kaynakları olan bilgisayarlarda adil erişim sağlayarak daha az sorunlu olur; Bununla birlikte, kaynakların verimli kullanımı sağlayarak daha sorunlu hale gelir.

Preemptive çekirdek modu Zamanlayıcı planlama kararları vermek için bu işletim sisteminde yararlanmayı uygulama kodu gerektirir. Buna karşılık, bir kullanıcı modu ortak scheduler kendi planlama kararları vermek uygulama kodu sağlar. İşbirlikçi planlama uygulama tarafından çok sayıda planlama kararlarına sağladığından çok çekirdek modu eşitleme ile ilişkili ek yükü azaltır. Zamanlamak için diğer işleri olduğunda ortak scheduler, genellikle işletim sistemi çekirdeği için zamanlama kararlarını erteleyen. Ortak scheduler çekirdeğe bildiriliyor engelleyici bir işlem yoktur ancak işlem, kullanıcı modu Zamanlayıcı bildiriliyor değil de işletim sistemi zamanlayıcı erteler.

### <a name="cooperative-scheduling-and-efficiency"></a>İşbirlikçi zamanlama ve verimliliği

Preemptive bir zamanlayıcı için aynı öncelik düzeyine sahip tüm iş eşittir. Preemptive Zamanlayıcı genellikle iş parçacığı içinde oluşturuldukları sırada zamanlar. Ayrıca, preemptive Zamanlayıcı iş parçacığı önceliği temelinde hepsini bir kez deneme şekilde, bir zaman dilimi her iş parçacığı sağlar. Bu mekanizma (her iş parçacığı ilerleme sağlar) eşitliği sağlasa da, verimliliği bazı maliyetle birlikte gelir. Örneğin, çok sayıda hesaplama yoğunluklu algoritmaları eşitliği gerektirmez. Bunun yerine, ilgili görevleri genel az sürede tamamlamanız önemlidir. İşbirlikçi zamanlama çalışması daha verimli bir şekilde zamanlamak bir uygulama sağlar. Örneğin, birçok iş parçacığı olan bir uygulama düşünün. Eşzamanlı olarak çalıştırılmasını kaynakların paylaşmayan iş parçacıklarını zamanlama, eşitleme ek yükü azaltmak ve böylelikle verimliliği artırabilirsiniz. Böylece her bir işlem hattı aşama girişi bellek önbelleğe zaten yüklü olan görevleri zamanlamak için başka bir etkin görevlerin işlem hatları (burada her görev, Öncekine çıkışı üzerinde çalışır) çalıştırmak için aynı işlemci üzerinde yoludur.

### <a name="using-preemptive-and-cooperative-scheduling-together"></a>PreEmptive ve işbirlikçi birlikte zamanlama kullanma

İşbirlikçi zamanlama tüm zamanlama sorunları çözer değil. Örneğin, görevler diğer görevlere oldukça yield değil tüm kullanılabilir bilgi işlem kaynaklarını tüketebilir ve ilerleme kaydetmesinin diğer görevleri engellemek. Eşzamanlılık Çalışma zamanı işbirlikçi zamanlama verimliliği avantajları preemptive zamanlama eşitliği garanti tamamlamak üzere kullanır. Varsayılan olarak, bir işi kaplayan algoritması verimli bir şekilde bilgi işlem kaynaklarını aralarında iş dağıtmak için kullandığı işbirlikçi Zamanlayıcı'yı eşzamanlılık çalışma zamanı sağlar. Ancak, eşzamanlılık çalışma zamanı Zamanlayıcısı'nı da oldukça kaynakları uygulamalar arasında dağıtmak için işletim sisteminin preemptive Zamanlayıcı kullanır. İş parçacığı üzerinde ayrıntılı denetim oluşturmak için uygulamalarınızda özel zamanlayıcılar ve Zamanlayıcı ilkeleri de oluşturabilirsiniz.

[[Üst](#top)]

##  <a name="winapi"></a> Eşzamanlılık Çalışma zamanı için Windows API ile karşılaştırma

Genellikle Windows API olarak adlandırılır (ve eski Win32 bilinir), Microsoft Windows uygulama programlama arabirimi, uygulamalarınızda eşzamanlılık sağlayan bir programlama modeli sağlar. Eşzamanlılık Çalışma zamanı, alttaki işletim sisteminden bulunmayan ek programlama modelleri sağlamak için Windows API üzerine inşa edilmiştir.

Eşzamanlılık Çalışma Zamanı paralel çalışmayı gerçekleştirmek için Windows API iş parçacığı modeli oluşturur. Ayrıca, Windows API bellek yönetimi ve iş parçacığı-yerel depolamayı mekanizmalarını kullanır. Windows 7 ve Windows Server 2008 R2 üzerinde kullanıcı zamanlanabilen iş parçacıklarını ve 64'ten fazla donanım iş parçacıklarının olan bilgisayarlar için Windows API desteği kullanır. Eşzamanlılık Çalışma zamanı Windows API modelini, işbirlikçi Görev Zamanlayıcısı'nı ve işi kaplayan bir algoritma bilgi işlem kaynaklarının kullanımını en üst düzeye çıkarmak için sağlayarak ve birden çok eş zamanlı Zamanlayıcı örnekleri sağlayarak genişletir.

### <a name="programming-languages"></a>Programlama dilleri

Windows API, programlama modeli kullanıma sunmak için C programlama dilini kullanır. Eşzamanlılık Çalışma zamanı C++ dilinde en yeni özelliklerinden yararlanır bir C++ programlama arabirimi sağlar. Örneğin, lambda işlevleri paralel iş işlevlerini tanımlama için birleştiren, tür kullanımı uyumlu bir mekanizma sağlar. Eşzamanlılık Çalışma zamanı kullanan en yeni C++ özellikleri hakkında daha fazla bilgi için bkz. [genel bakış](../../parallel/concrt/asynchronous-message-blocks.md).

### <a name="threads-and-thread-pools"></a>İş parçacıkları ve iş parçacığı havuzları

İş parçacığı Windows API merkezi eşzamanlılık mekanizmadır. Tipik olarak kullandığınız [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) iş parçacığı oluşturmak için işlevi. İş parçacığı oluşturma ve kullanma daha kolay olsa da, işletim sistemi önemli miktarda zaman ve bunları yönetmek için diğer kaynakları ayırır. Her iş parçacığı aynı öncelik düzeyinde başka bir iş parçacığıyla aynı yürütme süresi almak için garanti edilir olsa da, ayrıca, ilişkili ek yükü, yeterince geniş kapsamlı görevlerin oluşturmanız gerekir. Daha küçük ya da daha ayrıntılı görevler için eşzamanlılık ile ilişkili ek yükü görevleri paralel olarak çalışan avantajından daha fazla olabilir.

İş parçacığı havuzu iş parçacığı Yönetim maliyetini azaltmak için bir yoludur. Özel iş parçacığı havuzları ve her ikisini de etkinleştirmek küçük iş öğeleri verimli bir şekilde paralel olarak çalıştırmak Windows API tarafından sağlanan iş parçacığı havuzu uygulaması. Windows iş parçacığı havuzu iş öğeleri, ilk giren ilk çıkar (FIFO) kuyruktaki tutar. Her iş öğesi, havuza eklenen sırayla başlatılır.

Eşzamanlılık Çalışma zamanı zamanlama mekanizmasını FIFO genişletmek için işi kaplayan bir algoritma uygular. Algoritma iş öğelerini dışında çalışan iş parçacığı henüz başlamamış görevleri taşır. İşi kaplayan algoritması iş yükleri dengelemek olsa da, ayrıca iş öğelerini düzenlenmesine izin neden olabilir. Bu sipariş işleme zaman gönderildiği olandan farklı bir sırada başlatmak bir iş öğesi neden olabilir. Bu yinelemeli algoritmalar ile kullanışlıdır daha iyi olduğu veri daha yeni görevler eskiler arasında paylaşılır, fırsat. İlk çalıştırma için yeni öğeleri alınıyor, daha az İsabetsiz Önbellek okuma sayısı ve büyük olasılıkla daha az sayfa hataları anlamına gelir.

İşletim sistemi açısından bakıldığında, iş çalarak adil değil. Ancak alt görevler arasındaki eşitliği her zaman önemli bir algoritma veya paralel olarak çalıştırmak için görev uygulama geliştirdiğinde, değildir. Önemli değildir, genel görevinin nasıl hızlı bir şekilde biten olur. Diğer algoritmalar için FIFO uygun zamanlama stratejisidir.

### <a name="behavior-on-various-operating-systems"></a>Çeşitli işletim sistemlerinde davranışı

Windows Vista'da yığın performansı geliştirildi dışında Windows XP ve Windows Vista, eşzamanlılık çalışma zamanı kullanan uygulamalar benzer şekilde davranır.

Windows 7 ve Windows Server 2008 R2 işletim sisteminin daha fazla eşzamanlılık ve ölçeklenebilirliği destekler. Örneğin, bu işletim sistemlerinin 64'ten fazla donanım iş parçacıklarının olan bilgisayarları destekler. Windows API kullanan mevcut bir uygulama bu yeni özelliklerden yararlanmak için değiştirilmesi gerekir. Ancak, otomatik olarak eşzamanlılık çalışma zamanı kullanan bir uygulamayı bu özellikleri kullanır ve değişiklik gerektirmez.

[Base.user mode_scheduling](https://msdn.microsoft.com/library/windows/desktop/dd627187)

[[Üst](#top)]

##  <a name="openmp"></a> Eşzamanlılık çalışma zamanını OpenMP karşılaştırma

Eşzamanlılık Çalışma zamanı, çeşitli programlama modelleri sağlar. Bu modeller çakışmamalıdır veya diğer kitaplıkları modelleri tamamlar. Bu bölüm için eşzamanlılık çalışma zamanı karşılaştırır [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp).

OpenMP programlama modeli, açık bir standart tarafından tanımlanır ve Fortran ve C/C++ programlama dilleri için iyi tanımlanmış bağlamaları vardır. OpenMP sürümleri 2.0 ve 2.5 yinelemeli paralel algoritmalar için çok uygundur; diğer bir deyişle, bunlar paralel yineleme bir veri dizisi üzerinde gerçekleştirin. Paralellik derecesini önceden belirlenir ve sistemin kullanılabilir kaynaklara eşleşen OpenMP en etkili yoldur. OpenMP için yüksek performanslı bilgi işlem, özellikle de iyi bir eşleşme büyük işlem sorunları tek bir bilgisayarın işlem kaynakları arasında dağıtıldığı modelidir. Bu senaryoda, donanım ortamı denir ve geliştirici algoritma yürütüldüğünde, bilgi işlem kaynakları için özel erişim sağlamak makul bekleyebilirsiniz.

Ancak, diğer kısıtlanmış bilgi işlem ortamlarının daha az OpenMP için iyi bir eşleşme olmayabilir. Örneğin, özyinelemeli sorunları (örneğin, Hızlı sıralama algoritmasını veya bir veri ağacı arama) OpenMP uygulamak daha zordur. Eşzamanlılık Çalışma zamanı sağlayarak OpenMP özelliklerini tamamlar [paralel desenler Kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL) ve [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md). OpenMP, eşzamanlılık çalışma zamanı için kullanılabilir kaynaklar uyum sağlar ve iş yükü değiştikçe paralellik derecesini ayarlayan bir dinamik Zamanlayıcı sağlar.

Eşzamanlılık Çalışma zamanındaki özelliklerin çoğu uzatabilirsiniz. Ayrıca, yeni bir tane oluşturmak için var olan özellikler birleştirebilirsiniz. OpenMP derleyici yönergelerinde kullandığından, kolayca genişletilemez.

Eşzamanlılık Çalışma zamanı karşılaştırır OpenMP ve Eşzamanlılık Çalışma zamanı kullanmak için mevcut OpenMP kod geçirme hakkında daha fazla bilgi için bkz: [OpenMP döngüsünden eşzamanlılık çalışma zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md).

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)<br/>
[Genel bakış](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp)
