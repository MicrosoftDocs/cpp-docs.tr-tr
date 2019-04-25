---
title: Görev Zamanlayıcı (Eşzamanlılık Çalışma Zamanı)
ms.date: 11/04/2016
helpviewer_keywords:
- oversubscription [Concurrency Runtime]
- task scheduler [Concurrency Runtime], oversubscription
- schedule groups [Concurrency Runtime]
- task scheduler [Concurrency Runtime], lightweight tasks
- task scheduler [Concurrency Runtime]
- lightweight tasks [Concurrency Runtime]
- task scheduler [Concurrency Runtime], scheduler policies
- task scheduler [Concurrency Runtime], schedule groups
- wait function [Concurrency Runtime]
- task scheduler [Concurrency Runtime], scheduler instances
- scheduler instances [Concurrency Runtime]
- scheduler policies [Concurrency Runtime]
- task scheduler [Concurrency Runtime], wait function
ms.assetid: 9aba278c-e0c9-4ede-b7c6-fedf7a365d90
ms.openlocfilehash: c5d37d320344d2ebf83be2c939f5a7372d4af306
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180062"
---
# <a name="task-scheduler-concurrency-runtime"></a>Görev Zamanlayıcı (Eşzamanlılık Çalışma Zamanı)

Belgelerin bu bölümündeki konular eşzamanlılık çalışma zamanı Görev Zamanlayıcı'yı önemli özelliklerini açıklar. Görev Zamanlayıcısı'nı eşzamanlılık çalışma zamanı kullanan mevcut kod performansını ince ayar yapmak istediğinizde yararlıdır.

> [!IMPORTANT]
>  Görev Zamanlayıcısı'nı bir evrensel Windows Platformu (UWP) uygulaması kullanılabilir değil. Daha fazla bilgi için [oluşturma zaman uyumsuz işlemler c++ UWP uygulamaları için](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).
>
>  Visual Studio 2015 ve sonraki sürümlerinde, [concurrency::task](../../parallel/concrt/reference/task-class.md) sınıfı ve ilgili türü ppltasks.h kendi Zamanlayıcı olarak Windows işten kullanın. Bu konu, artık ppltasks.h içinde tanımlanan türler için geçerlidir. Parallel_for gibi paralel algoritmalar eşzamanlılık çalışma zamanı varsayılan Zamanlayıcı kullanmaya devam edin.

> [!TIP]
>  Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağlar ve bu nedenle, bir uygulama oluşturmak için gerekli değildir. Görev Zamanlayıcısı'nı, uygulamalarınızın performansını ayarlamanıza yardımcı olduğundan, ile başlamanızı öneririz [paralel desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanıyorsanız Yeni eşzamanlılık çalışma zamanı.

Görev Zamanlayıcısı'nı zamanlar ve çalışma zamanında görevleri koordine eder. A *görev* belirli bir işi yapan iş birimidir. Bir görev genellikle diğer görevlerle Paralel çalıştırabilirsiniz. Görev grubu öğeleri, paralel algoritmalar ve zaman uyumsuz aracılar tarafından gerçekleştirilen iş görevleri tüm örnekleri mevcuttur.

Görev Zamanlayıcı görevleri birden fazla hesaplama kaynağı olan bilgisayarlarda verimli bir şekilde zamanlamayla ilgili ayrıntıları yönetir. Görev Zamanlayıcısı'nı temel işletim sisteminin en yeni özellikleri de kullanır. Bu nedenle, otomatik olarak eşzamanlılık çalışma zamanı kullanan uygulamaları ölçeklendirin ve genişletilmiş yetenekler donanımda geliştirmek.

[Diğer eşzamanlılık modelleriyle karşılaştırma](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md) preemptive ve işbirlikçi zamanlama mekanizması arasındaki farklar açıklanmaktadır. Görev Zamanlayıcısı'nı kaynakları işleme en fazla kullanım elde etmek için işbirlikçi zamanlama ve işletim sisteminin preemptive Zamanlayıcı ile birlikte bir işi kaplayan algoritması kullanır.

Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağladığından altyapı ayrıntılarını yönetmek zorunda değilsiniz. Bu nedenle, genellikle Görev Zamanlayıcısı'nı doğrudan kullanmayın. Ancak, uygulamanızın kalitesini ihtiyaçlarını karşılamak için kendi zamanlama ilkesi veya ilişkilendirme zamanlayıcılar ile belirli görevleri sağlamak için Görev Zamanlayıcısı'nı kullanabilirsiniz. Örneğin, dört işlemci ölçeklenmez yordam sıralama paralel olduğunu varsayalım. Kullanabileceğiniz *Zamanlayıcı ilkeleri* dörtten fazla eşzamanlı kodlama görevinin oluşturduğu Zamanlayıcı oluşturma. Sıralama rutini Bu zamanlayıcı üzerinde çalışan diğer etkin zamanlayıcılar kalan tüm işlem kaynaklarını kullanmayı sağlar.

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Zamanlayıcı Örnekleri](../../parallel/concrt/scheduler-instances.md)|Zamanlayıcı örnekleri ve nasıl kullanılacağını açıklar `concurrency::Scheduler` ve `concurrency::CurrentScheduler` bunları yönetmek için sınıflar. Zamanlayıcı örnekleri açık zamanlama ilkeleri belirli türlerdeki iş yükleri ile ilişkilendirmek istediğiniz kullanın.|
|[Scheduler İlkeleri](../../parallel/concrt/scheduler-policies.md)|Zamanlayıcı ilkeleri rolünü açıklar. Zamanlayıcı ilkeleri görevleri yönettiğinde, Zamanlayıcı kullanan stratejisi kontrol etmek istediğinizde kullanın.|
|[Zamanlama Grupları](../../parallel/concrt/schedule-groups.md)|Zamanlama grupları rolünü açıklar. İlgili görevleri bir grup olduğunda yerleşim yeri görevler arasında yüksek derecede gibi gerek duyduğunuzda kullanın zamanlama grupları, aynı işlemci düğümde yürütülmesini yararlanır.|
|[Basit Görevler](../../parallel/concrt/lightweight-tasks.md)|Basit görevler rolünü açıklar. Eşzamanlılık Çalışma zamanı zamanlama işlevselliğini kullanmak için mevcut kodu uyarlamak için basit görevler yararlıdır.|
|[Bağlamlar](../../parallel/concrt/contexts.md)|Kapsamları rolünü açıklar `concurrency::wait` işlevi ve `concurrency::Context` sınıfı. Bu işlev, ne zaman bağlamları blok, engellemesini kaldırmak ve yield veya uygulamanızdaki gecikmeyi etkinleştirmek istediğiniz zaman denetime ihtiyacınız olduğunda kullanın.|
|[Bellek Yönetimi İşlevleri](../../parallel/concrt/memory-management-functions.md)|Açıklar `concurrency::Alloc` ve `concurrency::Free` işlevleri. Bu işlevler bellek ayırma ve eş zamanlı bir şekilde bellek boşaltma performansını geliştirebilirsiniz.|
|[Diğer eşzamanlılık modelleriyle karşılaştırma](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)|Preemptive ve işbirlikçi zamanlama mekanizması arasındaki farklar açıklanmaktadır.|
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Çeşitli paralel desenler, örneğin, paralel algoritmalar uygulamalarınıza kullanmayı açıklar.|
|[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)|Zaman uyumsuz aracılar uygulamalarınızda kullanmayı açıklar.|
|[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)|Eşzamanlılık paralel programlama basitleştirir ve ilgili konulara bağlantılar içeren çalışma zamanı, açıklar.|
