---
title: Eşzamanlılık Çalışma Zamanına Genel Bakış
ms.date: 11/19/2018
helpviewer_keywords:
- Concurrency Runtime, requirements
- Concurrency Runtime, architecture
- Concurrency Runtime, overview
- Concurrency Runtime, lambda expressions
ms.assetid: 56237d96-10b0-494a-9cb4-f5c5090436c5
ms.openlocfilehash: b50c943bb83c587ab4001556b1143f9d5f868a0b
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142927"
---
# <a name="overview-of-the-concurrency-runtime"></a>Eşzamanlılık Çalışma Zamanına Genel Bakış

Bu belgede Eşzamanlılık Çalışma Zamanı bir genel bakış sunulmaktadır. Eşzamanlılık Çalışma Zamanı avantajları, ne zaman kullanılacağı ve bileşenlerinin birbirleriyle ve işletim sistemi ile uygulamalarla nasıl etkileşime gireceğini açıklar.

## <a name="top"></a>Başlıklı

Bu belgede aşağıdaki bölümler yer alır:

- [Eşzamanlılık Çalışma Zamanı uygulama geçmişi](#dlls)

- [Eşzamanlılık için çalışma zamanının neden önemli olduğunu](#runtime)

- [Mimari](#architecture)

- [C++Lambda Ifadeleri](#lambda)

- [Requirements](#requirements)

## <a name="dlls"></a>Eşzamanlılık Çalışma Zamanı uygulama geçmişi

Visual Studio 2010 ile 2013 arasında, Eşzamanlılık Çalışma Zamanı Msvcr120. dll aracılığıyla Msvcr100. dll içinde eklenmiştir.  Visual Studio 2015 ' de UıCRT yeniden düzenlemesi gerçekleştiği zaman, bu DLL üç parçaya yeniden düzenlenmiş.

- uıcrtbase. dll – C API, Windows 10 ' da ve Windows Update ile alt düzey olarak sevk edilen

- vcruntime140. dll – Visual Studio ile gönderilen derleyici desteği işlevleri ve EH çalışma zamanı

- concrt140. dll – Eşzamanlılık Çalışma Zamanı, Visual Studio aracılığıyla gönderilir. `concurrency::parallel_for`gibi paralel kapsayıcılar ve algoritmalar için gereklidir. Ayrıca, Windows XP 'nin koşul değişkenleri olmadığından STL, Windows XP 'de bu DLL 'yi Power Synchronization temel elemanlarına gerektirir.

Visual Studio 2015 ve sonraki sürümlerde, Eşzamanlılık Çalışma Zamanı Görev Zamanlayıcı artık görev sınıfı için Zamanlayıcı ve ppltasks. h içindeki ilgili türler değildir. Bu türler artık Windows iş parçacığı kullanımını daha iyi performans ve Windows eşitleme temelleri ile birlikte çalışabilirlik için kullanır.

## <a name="runtime"></a>Eşzamanlılık için çalışma zamanının neden önemli olduğunu

Eşzamanlılık için bir çalışma zamanı, aynı anda çalışan uygulamalar ve uygulama bileşenlerine ilişkin bir tutarlılık ve öngörülebilirlik sağlar. Eşzamanlılık Çalışma Zamanı avantajlarına yönelik iki örnek *birlikte çalışırken görev zamanlama* ve *işbirliği engelleme*.

Eşzamanlılık çalışma zamanı, işlem kaynakları arasında çalışmayı verimli bir şekilde dağıtmak için bir iş hırsızlığı algoritması uygulayan bir işbirlikçi görev zamanlayıcısını kullanır. Örneğin, her ikisi de aynı çalışma zamanı tarafından yönetilen iki iş parçacığına sahip olan bir uygulamayı düşünün. Bir iş parçacığı zamanlanan görevini tamamlarsa, diğer iş parçacığından iş yükünü devreedebilir. Bu mekanizma, uygulamanın genel iş yükünü dengeler.

Eşzamanlılık Çalışma Zamanı Ayrıca, kaynaklara erişimi eşitlemek için birlikte çalışırken engellemeyi kullanan eşitleme temelleri de sağlar. Örneğin, paylaşılan bir kaynağa özel erişimi olması gereken bir görevi göz önünde bulundurun. Çalışma zamanı, birlikte çalışırken, diğer bir görevi kaynak için beklediği sürece diğer bir görevi gerçekleştirmek için geri kalan hisse kullanımını kullanabilir. Bu mekanizma, bilgi işlem kaynaklarının en yüksek kullanımını yükseltir.

[[Üst](#top)]

## <a name="architecture"></a>Mimarisini

Eşzamanlılık Çalışma Zamanı dört bileşene bölünür: paralel Desenler kitaplığı (PPL), zaman uyumsuz aracılar Kitaplığı, Görev Zamanlayıcı ve Kaynak Yöneticisi. Bu bileşenler, işletim sistemi ve uygulamalar arasında bulunur. Aşağıdaki çizim Eşzamanlılık Çalışma Zamanı bileşenlerinin işletim sistemi ve uygulamalar arasında nasıl etkileşime gireceğini göstermektedir:

**Eşzamanlılık Çalışma Zamanı mimarisi**

![Eşzamanlılık Çalışma Zamanı mimarisi](../../parallel/concrt/media/concurrencyrun.png "Eşzamanlılık Çalışma Zamanı mimarisi")

> [!IMPORTANT]
> Görev Zamanlayıcı ve Kaynak Yöneticisi bileşenleri, bir Evrensel Windows Platformu (UWP) uygulamasından veya ppltasks. h içinde görev sınıfını ya da başka türler kullandığınızda kullanılamaz.

Eşzamanlılık Çalışma Zamanı yüksek düzeyde *birleştirilebilir*, diğer bir deyişle, var olan işlevleri birleştirerek daha fazla bilgi alabilirsiniz. Eşzamanlılık Çalışma Zamanı, alt düzey bileşenlerden paralel algoritmalar gibi birçok özelliğe sahiptir.

Eşzamanlılık Çalışma Zamanı Ayrıca, kaynaklara erişimi eşitlemek için birlikte çalışırken engellemeyi kullanan eşitleme temelleri de sağlar. Bu eşitleme temelleri hakkında daha fazla bilgi için bkz. [eşitleme veri yapıları](../../parallel/concrt/synchronization-data-structures.md).

Aşağıdaki bölümler, her bir bileşenin sağladığı ve ne zaman kullanılacağı hakkında kısa bir genel bakış sağlar.

### <a name="parallel-patterns-library"></a>Paralel Desen Kitaplığı

Paralel Desenler kitaplığı (PPL), hassas paralellik gerçekleştirmeye yönelik genel amaçlı kapsayıcılar ve algoritmalar sağlar. PPL, koleksiyonlara veya bilgi işlem kaynakları genelinde veri kümelerine hesaplamalar dağıtan paralel algoritmalar sunarak, zorunlu *veri paralelliğini* sağlar. Ayrıca, bilgi işlem kaynakları arasında birden çok bağımsız işlem dağıtan görev nesneleri sağlayarak *görev paralelliğini* sağlar.

Paralel yürütmeden faydalanabilir bir yerel hesapladığınızda, paralel Desenler kitaplığını kullanın. Örneğin, mevcut bir `for` döngüsünü paralel olarak çalışacak şekilde dönüştürmek için [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını kullanabilirsiniz.

Paralel Desenler Kitaplığı hakkında daha fazla bilgi için bkz. [paralel Desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md).

### <a name="asynchronous-agents-library"></a>Zaman Uyumsuz Aracılar Kitaplığı

Zaman uyumsuz aracılar Kitaplığı (veya yalnızca *aracılar Kitaplığı*), hem aktör tabanlı bir programlama modeli hem de bir ileti geçirerek kaba veri akışı ve ardışık düzen oluşturma görevleri için arabirimler sağlar. Zaman uyumsuz aracılar, diğer bileşenler veri beklerken iş gerçekleştirerek gecikme süresini üretken hale getirmenize olanak tanır.

Birbiriyle zaman uyumsuz olarak iletişim kuran birden fazla varlık varsa aracılar kitaplığını kullanın. Örneğin, bir dosya veya ağ bağlantısından verileri okuyan bir aracı oluşturabilir ve ardından bu verileri başka bir aracıya göndermek için arabirimleri geçirme iletisini kullanabilirsiniz.

Aracılar Kitaplığı hakkında daha fazla bilgi için bkz. [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md).

### <a name="task-scheduler"></a>Görev Zamanlayıcısı

Görev Zamanlayıcı çalışma zamanında görevleri zamanlar ve düzenler. Görev Zamanlayıcı işbirliği yapılır ve en yüksek işlem kaynakları kullanımını sağlamak için bir iş hırsızlığı algoritması kullanır.

Eşzamanlılık Çalışma Zamanı, altyapı ayrıntılarını yönetmek zorunda kalmaması için varsayılan bir Zamanlayıcı sağlar. Ancak, uygulamanızın kalite ihtiyaçlarını karşılamak için kendi zamanlama ilkenizi da sağlayabilir veya belirli Zamanlayıcılar belirli görevlerle ilişkilendirebilirsiniz.

Görev Zamanlayıcı hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

### <a name="resource-manager"></a>Kaynak Yöneticisi

Kaynak Yöneticisi rolü, işlemciler ve bellek gibi bilgi işlem kaynaklarını yönetmez. Kaynak Yöneticisi, iş yüklerine, kaynakları en etkili olabilecekleri yere atayarak çalışma zamanında değiştikleri zaman yanıt verir.

Kaynak Yöneticisi, bilgi işlem kaynakları üzerinde bir soyutlama görevi görür ve öncelikle Görev Zamanlayıcı ile etkileşime girer. Kitaplıkları ve uygulamalarınızın performansını ince ayar yapmak için Kaynak Yöneticisi kullanabilseniz de, genellikle paralel Desenler kitaplığı, aracılar Kitaplığı ve Görev Zamanlayıcı tarafından sunulan işlevleri kullanırsınız. Bu kitaplıklar iş yükleri değiştiğinde kaynakları dinamik olarak yeniden dengelemek için Kaynak Yöneticisi kullanır.

[[Üst](#top)]

## <a name="lambda"></a>C++ Lambda ifadeleri

Eşzamanlılık Çalışma Zamanı tarafından tanımlanan türlerin ve algoritmaların birçoğu, şablonlar olarak C++ uygulanır. Bu türlerden ve algoritmalardan bazıları, iş gerçekleştiren bir yordamın parametre olarak ele alır. Bu parametre bir Lambda işlevi, bir işlev nesnesi veya bir işlev işaretçisi olabilir. Bu varlıklar, *çalışma işlevleri* veya *çalışma yordamları*olarak da adlandırılır.

Lambda ifadeleri, paralel işleme için çalışma C++ işlevlerini tanımlamaya yönelik bir kısa yolu sağladığından önemli bir yeni görsel dil özelliğidir. İşlev nesneleri ve işlev işaretçileri, Eşzamanlılık Çalışma Zamanı mevcut kodunuzla birlikte kullanmanıza olanak sağlar. Ancak, sağladıkları güvenlik ve üretkenlik avantajları nedeniyle yeni kod yazdığınızda lambda ifadeleri kullanmanızı öneririz.

Aşağıdaki örnek, [concurrency::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasına birden çok çağrıda lambda işlevlerinin, işlev nesnelerinin ve işlev işaretçilerinin sözdizimini karşılaştırır. Her bir `parallel_for_each` çağrısı, [std:: Array](../../standard-library/array-class-stl.md) nesnesindeki her öğenin karesini hesaplamak için farklı bir teknik kullanır.

[!code-cpp[concrt-comparing-work-functions#1](../../parallel/concrt/codesnippet/cpp/overview-of-the-concurrency-runtime_1.cpp)]

**Output**

```Output
1
256
6561
65536
390625
```

İçindeki C++Lambda işlevleri hakkında daha fazla bilgi için bkz. [lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).

[[Üst](#top)]

## <a name="requirements"></a>Gereklilik

Aşağıdaki tabloda Eşzamanlılık Çalışma Zamanı her bir bileşeniyle ilişkili üst bilgi dosyaları gösterilmektedir:

|Bileşen|Üstbilgi Dosyaları|
|---------------|------------------|
|Paralel Desen Kitaplığı (PPL)|PPL. h<br /><br /> concurrent_queue. h<br /><br /> concurrent_vector.h|
|Zaman Uyumsuz Aracılar Kitaplığı|Agents. h|
|Görev Zamanlayıcısı|concrt. h|
|Kaynak Yöneticisi|concrtrm. h|

Eşzamanlılık Çalışma Zamanı [eşzamanlılık](../../parallel/concrt/reference/concurrency-namespace.md) ad alanında bildirilmiştir. (Bu ad alanı için bir diğer ad olan [eşzamanlılık](../../parallel/concrt/reference/concurrency-namespace.md)de kullanabilirsiniz.) `concurrency::details` ad alanı Eşzamanlılık Çalışma Zamanı çerçevesini destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

Eşzamanlılık Çalışma Zamanı, C çalışma zamanı kitaplığı 'nın (CRT) bir parçası olarak sağlanır. CRT kullanan bir uygulama oluşturma hakkında daha fazla bilgi için bkz. [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).

[[Üst](#top)]
