---
title: OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş
ms.date: 11/04/2016
helpviewer_keywords:
- Concurrency Runtime, migrating from OpenMP
- OpenMP, migrating to the Concurrency Runtime
ms.assetid: 9bab7bb1-e45d-44b2-8509-3b226be2c93b
ms.openlocfilehash: 78fa83c30bc55d82ffa5d2ba1e7d65472643f86b
ms.sourcegitcommit: ee0103752884425843556a19cf418a504dc3cd02
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2018
ms.locfileid: "53737630"
---
# <a name="migrating-from-openmp-to-the-concurrency-runtime"></a>OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş

Eşzamanlılık Çalışma zamanı, çeşitli programlama modelleri sağlar. Bu modeller çakışmamalıdır veya diğer kitaplıkları modelleri tamamlar. Belgelerin bu bölümü karşılaştırma [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp) eşzamanlılık çalışma zamanı ve Eşzamanlılık Çalışma zamanı kullanmak için mevcut OpenMP kod geçirme hakkında örnekler sunar.

OpenMP programlama modeli, açık bir standart tarafından tanımlanır ve Fortran ve C/C++ programlama dilleri için iyi tanımlanmış bağlamaları vardır. OpenMP sürümleri 2.0 ve Visual C++ derleyicisi tarafından desteklenen, 2.5, yinelemeli paralel algoritmalar için çok uygundur; diğer bir deyişle, bunlar paralel yineleme bir veri dizisi üzerinde gerçekleştirin. OpenMP 3.0 yinelemeli görevleri yanı sıra yinelemeli olmayan görevlerini destekler.

Paralellik derecesini önceden belirlenir ve sistemin kullanılabilir kaynaklara eşleşen OpenMP en etkili yoldur. OpenMP için yüksek performanslı bilgi işlem, özellikle de iyi bir eşleşme büyük işlem sorunları bir bilgisayarın işlem kaynakları arasında dağıtıldığı modelidir. Bu senaryoda, donanım ortamı genellikle sabittir ve geliştirici algoritma yürütüldüğünde, tüm bilgi işlem kaynaklarına özel erişim sağlamak makul bekleyebilirsiniz.

Ancak, daha az kısıtlanmış bilgi işlem ortamlarının OpenMP için iyi bir eşleşme olmayabilir. Örneğin, özyinelemeli sorunları (örneğin, Hızlı sıralama algoritmasını veya bir veri ağacı arama) OpenMP 2.0 ve 2.5 uygulamak daha zordur. Eşzamanlılık Çalışma zamanı sağlayarak OpenMP özelliklerini tamamlar [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) ve [paralel desenler Kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL). Zaman uyumsuz aracılar kitaplığı parçalı görevlerden destekler. PPL, daha fazla ayrıntılı Paralel Görevler destekler. Eşzamanlılık Çalışma zamanı, böylece uygulama mantığına odaklanabilir paralel olarak işlemlerini gerçekleştirmek için gerekli olan altyapıyı sağlar. Eşzamanlılık Çalışma zamanı çeşitli programlama modelleri sağladığından, ancak kendi ek yükü zamanlama OpenMP gibi diğer eşzamanlılık kitaplıkları daha büyük olabilir. Bu nedenle, eşzamanlılık çalışma zamanı kullanmak için mevcut OpenMP kod dönüştürdüğünüzde performans artımlı olarak sınamanızı öneririz.

## <a name="when-to-migrate-from-openmp-to-the-concurrency-runtime"></a>OpenMP döngüsünden eşzamanlılık çalışma zamanına geçirmek ne zaman

Eşzamanlılık Çalışma zamanı aşağıdaki durumlarda kullanmak için mevcut OpenMP kod geçirmek için avantajlı olabilir.

|Durumları|Eşzamanlılık Çalışma zamanı avantajları|
|-----------|-------------------------------------------|
|Genişletilebilir bir eş zamanlı programlama altyapısı gerektirir.|Eşzamanlılık Çalışma zamanındaki özelliklerin çoğu uzatabilirsiniz. Ayrıca, yeni bir tane oluşturmak için var olan özellikler birleştirebilirsiniz. OpenMP derleyici yönergelerinde kullandığından, kolayca genişletilemez.|
|Uygulamanızı birlikte engelleme avantaj elde edecektir.|Bir görev henüz kullanılabilir olmayan bir kaynak gerektirdiğinden engellediğinde, ilk görevi için kaynak beklerken eşzamanlılık çalışma zamanı diğer görevleri gerçekleştirebilirsiniz.|
|Uygulamanız, dinamik yük dengelemeden avantaj elde edecektir.|Eşzamanlılık Çalışma zamanı, iş yüklerini değiştirme gibi bilgi işlem kaynakları, ayırma ayarlayan bir zamanlama algoritması kullanır. Zamanlayıcı bir paralel bölgenin bilgi işlem kaynakları ayırırken OpenMP, bu kaynak ayırmalar hesaplama sabittir.|
|Özel durum işleme desteği gerektirir.|PPL, hem Azure içindeki hem bir paralel bölgenin veya döngü dışında özel durumları yakalama sağlar. OpenMP içinde döngü ve paralel bölgenin içinde özel durum işlemesi gerekir.|
|İptal mekanizması gerektirir.|PPL, hem tek tek görevler ve paralel iş ağaçları iptal etmek uygulamaları etkinleştirir. OpenMP kendi iptal mekanizması uygulamak için uygulama gerektiriyor.|
|Başladığı farklı bir bağlamda bitirebilen paralel kod gerektirir.|Eşzamanlılık Çalışma zamanı bir bağlamda, bir görevi başlatmak ve daha sonra bekleyin ya da başka bir bağlamda, bir görev iptal olanak tanır. OpenMP, tüm paralel iş başladığı bağlamında tamamlanmalıdır.|
|Gelişmiş hata ayıklama desteği gerektirir.|Visual Studio sağlar **Paralel Yığınlar** ve **Paralel Görevler** windows böylece bir kolayca daha çok iş parçacıklı uygulamalarda hata ayıklaması yapabilirsiniz.<br /><br /> Eşzamanlılık Çalışma zamanı desteği hata ayıklama hakkında daha fazla bilgi için bkz. [Using the Tasks Window](/visualstudio/debugger/using-the-tasks-window), [Paralel Yığınlar penceresini kullanma](/visualstudio/debugger/using-the-parallel-stacks-window), ve [izlenecek yol: Paralel uygulamada hata ayıklama](/visualstudio/debugger/walkthrough-debugging-a-parallel-application).|

## <a name="when-not-to-migrate-from-openmp-to-the-concurrency-runtime"></a>OpenMP döngüsünden eşzamanlılık çalışma zamanına geçirmek istemiyorsanız ne zaman

Eşzamanlılık Çalışma zamanı kullanmak için mevcut OpenMP kod geçirmek uygun olmayabilir, aşağıdaki durumlarda açıklanmaktadır.

|Durumları|Açıklama|
|-----------|-----------------|
|Uygulamanız zaten gereksinimlerinizi karşılar.|Geçerli hata ayıklama desteği ve uygulama performansı ile memnun kaldığınızda, geçiş uygun olmayabilir.|
|Çok az iş, paralel döngü gövdelerini gerçekleştirin.|Eşzamanlılık Çalışma zamanı Görev Zamanlayıcısı'nı yükü döngü gövdesi nispeten küçük olduğunda özellikle döngü gövdesi, Paralel yürütme avantajları üstesinden değil.|
|Uygulamanızı c dilinde yazılır.|Eşzamanlılık Çalışma zamanı C++ özelliklerinin kullandığından, tam olarak kullanmak için C uygulamayı sağlayan kod yazdığınızda olamaz, uygun olmayabilir.|

## <a name="related-topics"></a>İlgili Konular

[Nasıl yapılır: Eşzamanlılık Çalışma zamanı kullanmak üzere döngü için bir OpenMP paralelini dönüştürme](../../parallel/concrt/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime.md)

OpenMP kullanan temel bir döngü verilen [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) ve [için](../../parallel/openmp/reference/for-openmp.md) yönergeleri, eşzamanlılık çalışma zamanı kullanmak üzere dönüştürülmesi gösterilmektedir [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritma.

[Nasıl yapılır: Eşzamanlılık Çalışma zamanı kullanmak için İptali kullanan bir OpenMP döngüsünü dönüştürme](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)<br/>
Bir OpenMP verilen [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[için](../../parallel/openmp/reference/for-openmp.md) çalıştırmak için tüm yinelemeleri gerektirmeyen döngü eşzamanlılık çalışma zamanı iptal mekanizması kullanacak şekilde dönüştürme işlemini gösterir.

[Nasıl yapılır: Eşzamanlılık Çalışma zamanı kullanmak için özel durum işleme kullanan bir OpenMP döngüsünü dönüştürme](../../parallel/concrt/convert-an-openmp-loop-that-uses-exception-handling.md)<br/>
Bir OpenMP verilen [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[için](../../parallel/openmp/reference/for-openmp.md) özel durum işleme gerçekleştiren bir döngü eşzamanlılık çalışma zamanı özel durum işleme mekanizmasını kullanmak üzere nasıl dönüştürme yapılacağını gösterir.

[Nasıl yapılır: Eşzamanlılık Çalışma zamanı kullanmak için azaltma değişkeni kullanan bir OpenMP döngüsünü dönüştürme](../../parallel/concrt/convert-an-openmp-loop-that-uses-a-reduction-variable.md)<br/>
Bir OpenMP verilen [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[için](../../parallel/openmp/reference/for-openmp.md) kullanan döngüsünü [azaltma](../../parallel/openmp/reference/reduction.md) yan tümcesi, eşzamanlılık çalışma zamanı kullanmak üzere nasıl dönüştürme yapılacağını gösterir.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)<br/>
[OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp)<br/>
[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)

