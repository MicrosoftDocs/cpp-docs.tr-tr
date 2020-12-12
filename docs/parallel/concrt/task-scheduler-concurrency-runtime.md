---
description: 'Hakkında daha fazla bilgi edinin: Görev Zamanlayıcı (Eşzamanlılık Çalışma Zamanı)'
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
ms.openlocfilehash: db52b6714f5bdb96cb33aeea1bce1d92f5d5d4a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271388"
---
# <a name="task-scheduler-concurrency-runtime"></a>Görev Zamanlayıcı (Eşzamanlılık Çalışma Zamanı)

Belgelerinin bu bölümündeki konularda Eşzamanlılık Çalışma Zamanı Görev Zamanlayıcı önemli özellikler açıklanır. Görev Zamanlayıcı, Eşzamanlılık Çalışma Zamanı kullanan mevcut kodunuzun performansı üzerinde ince ayar yapmak istediğinizde faydalıdır.

> [!IMPORTANT]
> Görev Zamanlayıcı, Evrensel Windows Platformu (UWP) uygulamasından kullanılamaz. Daha fazla bilgi için bkz. [UWP uygulamaları Için C++ ' da zaman uyumsuz Işlemler oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).
>
> Visual Studio 2015 ve üzeri sürümlerde, [concurrency:: Task](../../parallel/concrt/reference/task-class.md) sınıfı ve ppltasks. h içindeki ilgili türler, zamanlayıcı olarak Windows ThreadPool 'ı kullanır. Bu konu, artık ppltasks. h içinde tanımlanan türler için geçerli değildir. Parallel_for gibi paralel algoritmalar varsayılan Zamanlayıcı olarak Eşzamanlılık Çalışma Zamanı kullanmaya devam eder.

> [!TIP]
> Eşzamanlılık Çalışma Zamanı varsayılan bir Zamanlayıcı sağlar ve bu nedenle uygulamanızda bir tane oluşturmanız gerekmez. Görev Zamanlayıcı uygulamalarınızın performansını hassas bir şekilde ayarlamanıza yardımcı olduğundan, Eşzamanlılık Çalışma Zamanı yeni başladıysanız [paralel Desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) ile başlamanız önerilir.

Görev Zamanlayıcı çalışma zamanında görevleri zamanlar ve düzenler. *Görev* , belirli bir işi gerçekleştiren bir iş birimidir. Bir görev, genellikle diğer görevlerle paralel olarak çalıştırılabilir. Görev grubu öğeleri, paralel algoritmalar ve zaman uyumsuz aracılar tarafından gerçekleştirilen iş, görevlerin tüm örnekleridir.

Görev Zamanlayıcı, birden çok bilgi işlem kaynağı bulunan bilgisayarlarda etkili bir şekilde zamanlama görevleriyle ilgili ayrıntıları yönetir. Görev Zamanlayıcı, temel alınan işletim sisteminin en yeni özelliklerini de kullanır. Bu nedenle, Eşzamanlılık Çalışma Zamanı kullanan uygulamalar, genişletilmiş özellikleri olan donanımlar üzerinde otomatik olarak ölçeklendirin ve geliştirir.

[Diğer eşzamanlılık modelleriyle karşılaştırma](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md) , preemptive ve işbirlikçi zamanlama mekanizmaları arasındaki farklılıkları açıklar. Görev Zamanlayıcı, işlem kaynaklarının en yüksek kullanımını sağlamak için birlikte çalışan zamanlamayı ve işletim sisteminin preemptive Scheduler ile birlikte bir iş hırsızlığı algoritmasını kullanır.

Eşzamanlılık Çalışma Zamanı, altyapı ayrıntılarını yönetmek zorunda kalmaması için varsayılan bir Zamanlayıcı sağlar. Bu nedenle, genellikle Görev Zamanlayıcı doğrudan kullanmayın. Ancak, uygulamanızın kalite ihtiyaçlarını karşılamak için, kendi zamanlama ilkenizi sağlamak veya zamanlayıcılar 'i belirli görevlerle ilişkilendirmek üzere Görev Zamanlayıcı kullanabilirsiniz. Örneğin, dört işlemciyi aşmayan bir paralel sıralama yordamınız olduğunu varsayalım. En fazla dört eşzamanlı görev üreten bir zamanlayıcı oluşturmak için *Zamanlayıcı ilkelerini* kullanabilirsiniz. Bu zamanlayıcının sıralama yordamını çalıştırmak, diğer etkin zamanlayıcılar kalan işlem kaynaklarını kullanmasına olanak sağlar.

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Zamanlayıcı örnekleri](../../parallel/concrt/scheduler-instances.md)|Zamanlayıcı örneklerini ve `concurrency::Scheduler` `concurrency::CurrentScheduler` bunları yönetmek için ve sınıflarının nasıl kullanılacağını açıklar. Açık zamanlama ilkelerini belirli iş yükleri türleriyle ilişkilendirmek istediğinizde Zamanlayıcı örnekleri kullanın.|
|[Zamanlayıcı Ilkeleri](../../parallel/concrt/scheduler-policies.md)|Zamanlayıcı ilkelerinin rolünü açıklar. Scheduler 'ın görevleri yönettiğinde kullandığı stratejiyi denetlemek istediğinizde Zamanlayıcı ilkelerini kullanın.|
|[Zamanlama grupları](../../parallel/concrt/schedule-groups.md)|Zamanlama gruplarının rolünü açıklar. Görevler arasında yüksek düzeyde yere ihtiyacınız olduğunda, örneğin, bir ilgili görev grubu aynı işlemci düğümünde yürütmeyi avantajı olduğunda zamanlama gruplarını kullanın.|
|[Hafif görevler](../../parallel/concrt/lightweight-tasks.md)|Hafif görevlerin rolünü açıklar. Basit görevler, Eşzamanlılık Çalışma Zamanı zamanlama işlevini kullanmak üzere mevcut kodu uyarlıyorsanız faydalıdır.|
|[Bağlamlar](../../parallel/concrt/contexts.md)|Bağlamlar, `concurrency::wait` işlev ve sınıf rolü tanımlar `concurrency::Context` . Bağlamlar engellenme, engellemeyi kaldırma, ve ödeme yaparken veya uygulamanızda fazla aboneliği etkinleştirmek istediğinizde bu işlevselliği kullanın.|
|[Bellek yönetimi Işlevleri](../../parallel/concrt/memory-management-functions.md)|`concurrency::Alloc`Ve işlevlerini açıklar `concurrency::Free` . Bu işlevler, belleği eşzamanlı bir şekilde ayırarak ve boşaltarak bellek performansını iyileştirebilir.|
|[Diğer eşzamanlılık modelleriyle karşılaştırma](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)|PreEmptive ve işbirlikçi zamanlama mekanizmaları arasındaki farkları açıklar.|
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Uygulamalarınızda paralel algoritmaların çeşitli paralel desenlerinin nasıl kullanılacağını açıklar.|
|[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)|Uygulamalarınızda zaman uyumsuz aracıların nasıl kullanılacağını açıklar.|
|[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)|Paralel programlamayı kolaylaştıran ve ilgili konuların bağlantılarını içeren Eşzamanlılık Çalışma Zamanı açıklar.|
