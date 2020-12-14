---
description: "Hakkında daha fazla bilgi edinin: OpenMP 'dan Eşzamanlılık Çalışma Zamanı 'e geçiş"
title: OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş
ms.date: 11/04/2016
helpviewer_keywords:
- Concurrency Runtime, migrating from OpenMP
- OpenMP, migrating to the Concurrency Runtime
ms.assetid: 9bab7bb1-e45d-44b2-8509-3b226be2c93b
ms.openlocfilehash: ab9b50f0cdebcc8fc601565dd19c5c2704c17d95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193090"
---
# <a name="migrating-from-openmp-to-the-concurrency-runtime"></a>OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş

Eşzamanlılık Çalışma Zamanı çeşitli programlama modellerine izin vermez. Bu modeller diğer kitaplıkların modellerini örtüşebilir veya tamamlayabilir. Bu bölümdeki belgeler, [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp) 'yi eşzamanlılık çalışma zamanı karşılaştırır ve mevcut OpenMP kodunun eşzamanlılık çalışma zamanı kullanmak için nasıl geçirileceğiyle ilgili örnekler sağlar.

OpenMP programlama modeli açık bir standart tarafından tanımlanır ve FORTRAN ve C/C++ programlama dillerinin iyi tanımlanmış bağlamaları vardır. Microsoft C++ derleyicisi tarafından desteklenen OpenMP sürümleri 2,0 ve 2,5, yinelemeli bir paralel algoritmalarda iyi uygundur; diğer bir deyişle, bir dizi veri üzerinde paralel yineleme gerçekleştirir. OpenMP 3,0, yinelemeli görevlere ek olarak, yinelemeli olmayan görevleri destekler.

Paralellik derecesi önceden belirleniyorsa ve sistemdeki kullanılabilir kaynaklarla eşleşiyorsa OpenMP en verimli yöntemdir. OpenMP modeli, çok büyük hesaplama sorunlarının bir bilgisayarın işlem kaynakları arasında dağıtıldığı, yüksek performanslı bilgi işlem için özellikle iyi bir eşleşmedir. Bu senaryoda, donanım ortamı genellikle sabittir ve geliştirici, algoritma yürütüldüğünde tüm bilgi işlem kaynaklarına özel erişime sahip olmasını makul bir şekilde bekleyebilir.

Ancak, daha az kısıtlanmış bilgi işlem ortamları OpenMP için iyi bir eşleşme olmayabilir. Örneğin, özyinelemeli sorunlar (Hızlı sıralama algoritması veya bir veri ağacı arama gibi), OpenMP 2,0 ve 2,5 kullanarak uygulanması daha zordur. Eşzamanlılık Çalışma Zamanı, [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) ve [paralel Desenler kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (ppl) sağlayarak OpenMP özelliklerini tamamlar. Zaman uyumsuz aracılar Kitaplığı, kaba görev paralelliğini destekler; PPL, daha hassas paralel görevleri destekler. Eşzamanlılık Çalışma Zamanı, uygulamanızın mantığına odaklanabilmeniz için, işlemleri paralel olarak gerçekleştirmek için gereken altyapıyı sağlar. Ancak, Eşzamanlılık Çalışma Zamanı çeşitli programlama modellerine izin sağladığından, zamanlama ek yükü OpenMP gibi diğer eşzamanlılık kitaplıklarından daha büyük olabilir. Bu nedenle, mevcut OpenMP kodunuzu Eşzamanlılık Çalışma Zamanı kullanmak üzere dönüştürürken performansı artımlı olarak test etmenizi öneririz.

## <a name="when-to-migrate-from-openmp-to-the-concurrency-runtime"></a>OpenMP 'dan Eşzamanlılık Çalışma Zamanı 'e geçiş yapılırken

Aşağıdaki durumlarda Eşzamanlılık Çalışma Zamanı kullanmak için mevcut OpenMP kodunu geçirmek avantajlı olabilir.

|Çalışmaların|Eşzamanlılık Çalışma Zamanı avantajları|
|-----------|-------------------------------------------|
|Genişletilebilir bir eşzamanlı programlama çerçevesine ihtiyacınız vardır.|Eşzamanlılık Çalışma Zamanı özelliklerin birçoğu genişletilebilir. Ayrıca, yeni yenilerini oluşturmak için var olan özellikleri birleştirebilirsiniz. OpenMP derleyici yönergelerini kullandığından, bu, kolayca genişletilemez.|
|Uygulamanız, ortaklaşa engellenmeden faydalanabilir.|Bir görev, henüz kullanılamayan bir kaynak gerektirdiğinden, ilk görevin kaynağı beklediği sırada Eşzamanlılık Çalışma Zamanı diğer görevleri gerçekleştirebilir.|
|Uygulamanız dinamik yük dengelemesinden faydalanabilir.|Eşzamanlılık Çalışma Zamanı, iş yükleri değiştiğinde bilgi işlem kaynaklarının ayrılmasını ayarlayan bir zamanlama algoritması kullanır. OpenMP 'de Zamanlayıcı, bir paralel bölgeye bilgi işlem kaynakları ayırdığında, bu kaynak ayırmaları hesaplama genelinde düzeltilir.|
|Özel durum işleme desteği gerekir.|PPL, paralel bir bölgenin veya döngünün içinde ve dışında özel durumları yakalamanızı sağlar. OpenMP 'de, paralel bölgenin veya döngünün içindeki özel durumu işlemeniz gerekir.|
|İptal mekanizması gerekir.|PPL, uygulamaların hem bireysel görevleri hem de paralel iş ağaçlarını iptal etmesini sağlar. OpenMP, uygulamanın kendi iptal mekanizmasını uygulamasını gerektirir.|
|Paralel kodun başladığı farklı bir bağlamda sonlanması gerekir.|Eşzamanlılık Çalışma Zamanı, bir görevi tek bir bağlamda başlatıp bu görevi başka bir bağlamda beklemenize veya iptal etmenize olanak tanır. OpenMP 'da, tüm paralel işler başladığı bağlamda bitmelidir.|
|Gelişmiş hata ayıklama desteği gerekir.|Çoklu iş parçacıklı uygulamalarda daha kolay hata ayıklamanıza olanak sağlamak için Visual Studio **Paralel Yığınlar** ve **paralel görevler** penceresi sağlar.<br /><br /> Eşzamanlılık Çalışma Zamanı için hata ayıklama desteği hakkında daha fazla bilgi için, bkz. [Görevler penceresini kullanma](/visualstudio/debugger/using-the-tasks-window), [Paralel Yığınlar penceresi kullanma](/visualstudio/debugger/using-the-parallel-stacks-window)ve [Izlenecek yol: paralel uygulamada hata ayıklama](/visualstudio/debugger/walkthrough-debugging-a-parallel-application).|

## <a name="when-not-to-migrate-from-openmp-to-the-concurrency-runtime"></a>OpenMP 'dan Eşzamanlılık Çalışma Zamanı geçiş yapmak için

Aşağıdaki durumlar, Eşzamanlılık Çalışma Zamanı kullanmak için mevcut OpenMP kodunu geçirmek için uygun olmayabilir.

|Çalışmaların|Açıklama|
|-----------|-----------------|
|Uygulamanız gereksinimlerinizi zaten karşılıyor.|Uygulama performansı ve geçerli hata ayıklama desteğiyle memnun kaldıysanız, geçiş uygun olmayabilir.|
|Paralel döngü gövdelerinizi az iş yapar.|Eşzamanlılık Çalışma Zamanı görev Scheduler 'ın ek yükü, özellikle döngü gövdesi görece küçük olduğunda, döngü gövdesinin paralel olarak yürütülmesi avantajlarının üstesinden gelmeyebilir.|
|Uygulamanız C dilinde yazılmıştır.|Eşzamanlılık Çalışma Zamanı birçok C++ özelliği kullandığından, C uygulamasının tam olarak kullanmasını sağlayan kodu yazamadığı zaman uygun olmayabilir.|

## <a name="related-topics"></a>İlgili Konular

[Nasıl yapılır: bir OpenMP Parallel for döngüsünü Eşzamanlılık Çalışma Zamanı kullanacak şekilde dönüştürme](../../parallel/concrt/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime.md)

OpenMP [Parallel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) [ve yönergeleri](../openmp/reference/openmp-directives.md#for-openmp) kullanan temel bir döngü verildiğinde, Eşzamanlılık Çalışma Zamanı [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını kullanmak için nasıl dönüştürüleceğini gösterir.

[Nasıl yapılır: Eşzamanlılık Çalışma Zamanı kullanmak için Iptali kullanan bir OpenMP döngüsünü dönüştürme](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)<br/>
Tüm yinelemelerin çalıştırılmasını gerektirmeyen bir OpenMP [Parallel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[for](../openmp/reference/openmp-directives.md#for-openmp) döngüsü verildiğinde, eşzamanlılık çalışma zamanı iptal mekanizmasını kullanmak için nasıl dönüştürüleceğini gösterir.

[Nasıl yapılır: Eşzamanlılık Çalışma Zamanı kullanmak için özel durum Işleme kullanan bir OpenMP döngüsünü dönüştürme](../../parallel/concrt/convert-an-openmp-loop-that-uses-exception-handling.md)<br/>
Özel durum işlemeyi gerçekleştiren bir OpenMP [Parallel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[for](../openmp/reference/openmp-directives.md#for-openmp) döngüsü verildiğinde, eşzamanlılık çalışma zamanı özel durum işleme mekanizmasını kullanmak üzere nasıl dönüştüleceğini gösterir.

[Nasıl yapılır: Eşzamanlılık Çalışma Zamanı kullanmak için azaltma değişkeni kullanan bir OpenMP döngüsünü dönüştürme](../../parallel/concrt/convert-an-openmp-loop-that-uses-a-reduction-variable.md)<br/>
[Azaltma](../openmp/reference/openmp-clauses.md#reduction) yan tümcesini kullanan bir OpenMP [Parallel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[for](../openmp/reference/openmp-directives.md#for-openmp) döngüsü verildiğinde, eşzamanlılık çalışma zamanı kullanmak için nasıl dönüştürüleceğini gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)<br/>
[OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp)<br/>
[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)
