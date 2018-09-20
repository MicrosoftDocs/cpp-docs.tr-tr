---
title: Eşzamanlılık çalışma zamanına genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 07/20/2018
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Concurrency Runtime, requirements
- Concurrency Runtime, architecture
- Concurrency Runtime, overview
- Concurrency Runtime, lambda expressions
ms.assetid: 56237d96-10b0-494a-9cb4-f5c5090436c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b837a68c1887254cd6ace9546a9c5175d1ee08a9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384506"
---
# <a name="overview-of-the-concurrency-runtime"></a>Eşzamanlılık Çalışma Zamanına Genel Bakış
Bu belge, eşzamanlılık çalışma zamanına genel bakış sağlar. Eşzamanlılık Çalışma zamanı avantajlarını açıklar ne zaman kullanılmalı ve bileşenlerinin birbirleriyle ve işletim sistemi ve uygulamalar ile nasıl etkileşim.

##  <a name="top"></a> Bölümleri

Bu belgede aşağıdaki bölümler yer alır:

- [Eşzamanlılık Çalışma zamanı uygulama geçmişi](#dlls)

- [Eşzamanlılık Çalışma Zamanı Modülü önemli neden?](#runtime)

- [Mimari](#architecture)

- [C++ Lambda ifadeleri](#lambda)

- [Gereksinimler](#requirements)

## <a name="dlls"></a> Eşzamanlılık Çalışma zamanı uygulama geçmişi

Eşzamanlılık Çalışma zamanı, 2013 aracılığıyla Visual Studio 2010'da msvcr100.dll msvcr120.dll aracılığıyla içinde dahil edilmiştir.  Bu DLL, yeniden düzenleme UCRT Visual Studio 2015'te oluştuğunda, üç bölüme yeniden düzenlenmeden:

- alt düzey aracılığıyla Windows Update - hizmet ve Windows 10'da sevk ucrtbase.dll – C API

- tetiklenen, vcruntime140.dll – derleyici işlevleri ve Visual Studio ile birlikte gelen EH çalışma zamanı desteği

- concrt140.dll – eşzamanlılık çalışma zamanı, Visual Studio ile birlikte gelir. Paralel kapsayıcılar ve algoritmalar için gibi gerekli `concurrency::parallel_for`. Ayrıca, Windows XP koşul değişkenleri olmadığından STL power eşitleme temellerine için bu DLL Windows XP gerektirir.

Visual Studio 2015 ve sonraki sürümlerinde, eşzamanlılık çalışma zamanı Görev Zamanlayıcısı'nı artık Zamanlayıcı görevi sınıfı ve ppltasks.h ilgili türü değil. Bu tür artık Windows işten daha iyi performans ve birlikte çalışabilirlik için Windows ile eşitleme temellerine kullanın.

##  <a name="runtime"></a> Eşzamanlılık Çalışma Zamanı Modülü önemli neden?

Eşzamanlılık için çalışma zamanı gerekmemesi ve uygulamaları ve aynı anda çalışan uygulama bileşenleri için öngörülebilirlik sağlar. Eşzamanlılık Çalışma zamanı avantajlarını iki örnek *işbirlikçi görev zamanlama* ve *birlikte engelleme*.

Eşzamanlılık Çalışma Zamanı İş bilgi işlem kaynakları arasında verimli bir şekilde dağıtmak için işi kaplayan bir algoritma uygulayan bir işbirlikçi Görev Zamanlayıcı kullanır. Örneğin, her ikisi de aynı çalışma zamanı tarafından yönetilen iki iş parçacığı olan bir uygulama düşünün. Bir iş parçacığı, zamanlanmış bir görev tamamlanırsa, diğer iş parçacığından iş boşaltabilirsiniz. Bu mekanizma, uygulamanın genel iş yükü dengeler.

Eşzamanlılık Çalışma zamanı kullanan birlikte engelleme kaynaklarına erişimi eşitlemek için eşitleme temellerine de sağlar. Örneğin, paylaşılan bir kaynağa özel erişim gereken görev göz önünde bulundurun. İşbirliği ile engelleyerek, çalışma zamanı, kaynak için ilk görev bekler gibi başka bir görevi gerçekleştirmek için kalan kuantum bant kitaplığını kullanabilirsiniz. Bu mekanizma, bilgi işlem kaynaklarının en fazla kullanım yükseltir.

[[Üst](#top)]

##  <a name="architecture"></a> Mimarisi

Eşzamanlılık Çalışma zamanı dört bileşene bölünür: paralel desenler kitaplığı (PPL), zaman uyumsuz aracılar kitaplığı, Görev Zamanlayıcısı'nı ve Resource Manager. Bu bileşenler işletim sistemi ve uygulamalar arasında yer alır. Aşağıdaki çizim, eşzamanlılık çalışma zamanı bileşenlerini işletim sistemi ve uygulamalar arasında nasıl etkileşim kurduğu gösterilmektedir:

**Eşzamanlılık Çalışma zamanı mimarisi**

![Eşzamanlılık Çalışma zamanı mimarisi](../../parallel/concrt/media/concurrencyrun.png "concurrencyrun")

> [!IMPORTANT]
>  Görev Zamanlayıcısı'nı ve Resource Manager bileşenleri, bir evrensel Windows Platformu (UWP) uygulamasına veya görev sınıfı ya da diğer türleri içinde ppltasks.h kullandığınızda kullanılamaz.

Eşzamanlılık Çalışma zamanı yüksek olduğu *birleştirilebilir*, diğer bir deyişle, daha fazlasını yapmak için var olan işlevselliği birleştirebilirsiniz. Eşzamanlılık Çalışma zamanı, alt düzey bileşenlerden paralel algoritmalar gibi birçok özellik oluşturur.

Eşzamanlılık Çalışma zamanı kullanan birlikte engelleme kaynaklarına erişimi eşitlemek için eşitleme temellerine de sağlar. Bu eşitleme temellerine hakkında daha fazla bilgi için bkz: [eşitleme veri yapıları](../../parallel/concrt/synchronization-data-structures.md).

Aşağıdaki bölümler, her bileşenin ne sağlar ve ne zaman kullanacağınız kısa bir genel bakış sağlar.

### <a name="parallel-patterns-library"></a>Paralel Desen Kitaplığı

Paralel Desen kitaplığı (PPL), hassas paralellik gerçekleştirmek için genel amaçlı kapsayıcılar ve algoritmalar sağlar. PPL sağlayan *kesinlik temelli veri paralelliği* sağlayarak bulut bilgi işlem kaynakları arasında veri kümelerini veya koleksiyonlar üzerinde hesaplamalar dağıtmak, paralel algoritmalar. Ayrıca *görev paralelliği* bilgi işlem kaynakları genelinde birden çok bağımsız işlem dağıttığınız görev nesnelerinin sağlayarak.

Paralel desenler kitaplığı, paralel yürütmeyi avantaj elde edebileceği bir yerel hesaplama sahip olduğunuzda kullanın. Örneğin, kullanabileceğiniz [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) varolan dönüştürmek için algoritma `for` döngü paralel olarak görev yapacak.

Paralel desen Kitaplığı hakkında daha fazla bilgi için bkz: [paralel desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md).

### <a name="asynchronous-agents-library"></a>Zaman Uyumsuz Aracılar Kitaplığı

Zaman uyumsuz aracılar kitaplığı (veya yalnızca *Aracılar Kitaplığı*) bir aktör tabanlı programlama modeli ve ileti geçirme arabirimler için parçalı veri akışı ve ardışık düzen oluşturma görevleri sağlar. Zaman uyumsuz aracılar üretken gecikme süresi için verileri diğer bileşenleri tamamlanmasını bekleyen iş gerçekleştirerek kullanabilmesine olanak tanır.

Agents kitaplığı, birbirleriyle zaman uyumsuz olarak iletişim birden fazla varlık olduğunda kullanın. Örneğin, bir dosya veya ağ bağlantısından veri okuyan ve ardından bu verileri başka bir aracıya göndermek için ileti arabirimleri geçirme kullanan bir aracı oluşturabilirsiniz.

Agents Kitaplığı hakkında daha fazla bilgi için bkz: [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md).

### <a name="task-scheduler"></a>Görev Zamanlayıcısı

Görev Zamanlayıcısı'nı zamanlar ve çalışma zamanında görevleri koordine eder. Görev Zamanlayıcısı'nı işbirliği yapan ve işlem kaynaklarının en yüksek kullanımı elde etmek için işi kaplayan bir algoritma kullanır.

Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağladığından altyapı ayrıntılarını yönetmek zorunda değilsiniz. Ancak, uygulamanızın kalitesini ihtiyaçlarını karşılamak için belirli görevler zamanlama kendi ilke veya ilişkilendirme özel planlayıcılar sağlayabilirsiniz.

Görev Zamanlayıcı hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

### <a name="resource-manager"></a>Kaynak Yöneticisi

Resource Manager'ın işlemci ve bellek gibi bilgi işlem kaynaklarını yönetmek üzere rolüdür. Çalışma zamanında burada en etkili olabilirler için kaynakları atayarak değiştiklerinde Resource Manager iş yükleri için yanıt verir.

Resource Manager bilgi işlem kaynakları bir Özet görev yapar ve öncelikli olarak Görev Zamanlayıcısı ile etkileşime geçer. Kitaplıkları ve uygulamaları performans üzerinde ince ayar için Kaynak Yöneticisi'ni kullanabilirsiniz, ancak genellikle paralel desenler kitaplığı, aracılar kitaplığı ve Görev Zamanlayıcı tarafından sağlanan işlevselliği kullandığı. Bu kitaplıklar, iş yüklerini değiştirme gibi kaynakları dinamik olarak yeniden dengelemek için Resource Manager kullanın.

[[Üst](#top)]

##  <a name="lambda"></a> C++ Lambda ifadeleri

Birçok türleri ve Eşzamanlılık Çalışma zamanı tarafından tanımlanan algoritmaları C++ şablonları uygulanır. Bu türleri ve algoritmaları bazıları işini gerçekleştiren bir yordam parametre olarak yararlanın. Bu parametre, bir lambda işlevi, bir işlev nesnesi veya bir işlev işaretçisi olabilir. Bu varlıklar, ayrıca olarak adlandırılır *iş işlevlerini* veya *çalışma yordamları*.

Bunlar paralel işleme iş işlevlerini birleştiren yolu sağladığından lambda ifadeleri bir önemli yeni Visual C++ dil özelliğidir. İşlev işaretçileri ve işlev nesneleri ile mevcut kodunuzu eşzamanlılık çalışma zamanı kullanmanıza olanak verir. Ancak, sağladıkları güvenlik ve üretkenlik avantajları nedeniyle yeni kod yazdığınızda, lambda ifadeleri kullanmanızı öneririz.

Aşağıdaki örnek, lambda işlevi, işlev nesneleri ve birden çok çağrı içindeki işlev işaretçileriyle söz dizimi karşılaştırır [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritması. Her çağrı `parallel_for_each` her öğe karesini işlem için farklı bir teknik kullanır bir [std::array](../../standard-library/array-class-stl.md) nesne.

[!code-cpp[concrt-comparing-work-functions#1](../../parallel/concrt/codesnippet/cpp/overview-of-the-concurrency-runtime_1.cpp)]

**Output**

```Output
1
256
6561
65536
390625
```

C++ lambda işlevleri hakkında daha fazla bilgi için bkz. [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).

[[Üst](#top)]

##  <a name="requirements"></a> Gereksinimleri

Eşzamanlılık Çalışma Zamanı'nın her bileşeninin ile ilişkili olan üstbilgi dosyaları aşağıdaki tabloda gösterilmiştir:

|Bileşen|Üstbilgi Dosyaları|
|---------------|------------------|
|Paralel Desen Kitaplığı (PPL)|ppl.h<br /><br /> concurrent_queue.h<br /><br /> concurrent_vector.h|
|Zaman Uyumsuz Aracılar Kitaplığı|Agents.h|
|Görev Zamanlayıcısı|concrt.h|
|Kaynak Yöneticisi|concrtrm.h|

Eşzamanlılık Çalışma zamanı içinde bildirildiği [eşzamanlılık](../../parallel/concrt/reference/concurrency-namespace.md) ad alanı. (Ayrıca [eşzamanlılık](../../parallel/concrt/reference/concurrency-namespace.md), bu ad alanı için bir diğer ad olduğu.) `concurrency::details` Ad alanı eşzamanlılık çalışma zamanı çerçevesi destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

Eşzamanlılık Çalışma zamanı, C çalışma zamanı kitaplığı (CRT) bir parçası olarak sağlanır. CRT kullanan bir uygulama oluşturma hakkında daha fazla bilgi için bkz. [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).

[[Üst](#top)]

