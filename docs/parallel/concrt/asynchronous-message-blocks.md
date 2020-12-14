---
description: 'Daha fazla bilgi edinin: zaman uyumsuz Ileti blokları'
title: Zaman Uyumsuz İleti Blokları
ms.date: 11/04/2016
helpviewer_keywords:
- non-greedy join [Concurrency Runtime]
- asynchronous message blocks
- greedy join [Concurrency Runtime]
ms.assetid: 79c456c0-1692-480c-bb67-98f2434c1252
ms.openlocfilehash: 7447d30932693eebe22d0a6f7f0aad0fba2abf16
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189151"
---
# <a name="asynchronous-message-blocks"></a>Zaman Uyumsuz İleti Blokları

Aracılar Kitaplığı, iletileri iş parçacığı güvenli bir şekilde uygulama bileşenleri arasında yaymanızı sağlayan çeşitli ileti bloğu türleri sağlar. Bu ileti bloğu türleri genellikle [eşzamanlılık:: Send](reference/concurrency-namespace-functions.md#send), [concurrency:: asend](reference/concurrency-namespace-functions.md#asend), [concurrency:: receive](reference/concurrency-namespace-functions.md#receive)ve [concurrency:: try_receive](reference/concurrency-namespace-functions.md#try_receive)gibi çeşitli ileti geçirme yordamları ile kullanılır. Aracılar Kitaplığı tarafından tanımlanan yordamları geçirme hakkında daha fazla bilgi için bkz. [Ileti geçirme işlevleri](../../parallel/concrt/message-passing-functions.md).

## <a name="sections"></a><a name="top"></a> Başlıklı

Bu konu aşağıdaki bölümleri içermektedir:

- [Kaynaklar ve Hedefler](#sources_and_targets)

- [İleti yayma](#propagation)

- [Ileti bloğu türlerine genel bakış](#overview)

- [unbounded_buffer sınıfı](#unbounded_buffer)

- [overwrite_buffer sınıfı](#overwrite_buffer)

- [single_assignment sınıfı](#single_assignment)

- [Call sınıfı](#call)

- [Transformatör sınıfı](#transformer)

- [seçim sınıfı](#choice)

- [Sınıfları Birleştir ve multitype_join](#join)

- [Timer sınıfı](#timer)

- [İleti filtreleme](#filtering)

- [İleti ayırma](#reservation)

## <a name="sources-and-targets"></a><a name="sources_and_targets"></a> Kaynaklar ve hedefler

Kaynaklar ve hedefler ileti geçirme konusunda iki önemli katılımcılardır. *Kaynak* , ileti gönderen bir iletişim uç noktasını ifade eder. *Hedef* , iletileri alan bir iletişim uç noktası anlamına gelir. Bir kaynağı, yazdığınız bir uç nokta olarak ve bir hedefin üzerine yazdığınız bitiş noktası olarak düşünebilirsiniz. Uygulamalar, *mesajlaşma ağlarını* biçimlendirmek için kaynakları ve hedefleri birbirine bağlama.

Aracılar Kitaplığı, kaynakları ve hedefleri temsil etmek için iki soyut sınıf kullanır: [concurrency:: ISource](../../parallel/concrt/reference/isource-class.md) ve [concurrency:: itarget](../../parallel/concrt/reference/itarget-class.md). Kaynak olarak davranan ileti bloğu türleri ' den türetilir `ISource` ; hedef olarak davranan ileti bloğu türleri öğesinden türetilir `ITarget` . Kaynak ve hedef gibi davranan ileti bloğu türleri hem hem de ' den türetilir `ISource` `ITarget` .

[[Üst](#top)]

## <a name="message-propagation"></a><a name="propagation"></a> İleti yayma

*İleti yayma* , bir bileşenden diğerine ileti gönderme işlemidir. İleti bloğuna bir ileti sunulduğunda, bu iletiyi kabul edebilir, reddedebilir veya erteleyebilir. Her ileti bloğu türü, iletileri farklı yollarla depolar ve iletir. Örneğin, `unbounded_buffer` sınıfı sınırsız sayıda ileti depoladığında, `overwrite_buffer` sınıf tek seferde tek bir ileti depolar ve transformatör sınıfı her iletinin değiştirilmiş bir sürümünü depolar. Bu ileti bloğu türleri bu belgenin ilerleyen bölümlerinde daha ayrıntılı açıklanmıştır.

İleti bloğu bir iletiyi kabul ettiğinde, isteğe bağlı olarak iş gerçekleştirebilir ve ileti bloğu bir kaynak ise, sonuç iletisini ağın başka bir üyesine geçirin. İleti bloğu, almasını istemediğiniz iletileri reddetmek için bir filtre işlevi kullanabilir. Filtreler, bu konunun ilerleyen bölümlerinde, [Ileti filtrelemesinde](#filtering)daha ayrıntılı bir şekilde açıklanmıştır. Bir iletiyi erteler bir ileti bloğu bu iletiyi ayırabilirler ve daha sonra tüketebilir. İleti ayırma, bu konunun ilerleyen kısımlarında, bölüm [Ileti ayırma](#reservation)bölümünde daha ayrıntılı olarak açıklanmıştır.

Aracılar Kitaplığı ileti bloklarının zaman uyumsuz veya zaman uyumlu olarak ileti geçişine olanak sağlar. İleti bloğuna zaman uyumlu bir ileti geçirdiğinizde, örneğin işlevini kullanarak, `send` hedef blok iletiyi kabul edene veya reddetene kadar çalışma zamanı geçerli bağlamı engeller. İleti bloğuna zaman uyumsuz bir ileti geçirdiğinizde, `asend` çalışma zamanı iletiyi hedefe sağlar ve hedef iletiyi kabul ediyorsa, çalışma zamanı iletiyi alıcıya yayan bir zaman uyumsuz görevi zamanlar. Çalışma zamanı, iletileri birlikte bir şekilde yaymak için hafif görevler kullanır. Hafif görevler hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

Uygulamalar, mesajlaşma ağlarını biçimlendirmek için kaynakları ve hedefleri birbirine bağlama. Genellikle, ağı bağlayabilir ve `send` `asend` ağa veri geçitirsiniz. Bir kaynak ileti bloğunu hedefe bağlamak için [concurrency:: ISource:: link_target](reference/isource-class.md#link_target) yöntemini çağırın. Kaynak bloğunun bir hedefle bağlantısını kesmek için [concurrency:: ISource:: unlink_target](reference/isource-class.md#unlink_target) yöntemini çağırın. Kaynak bloğunun tüm hedeflerinden bağlantısını kesmek için [eşzamanlılık:: ISource:: unlink_targets](reference/isource-class.md#unlink_targets) yöntemini çağırın. Önceden tanımlı ileti bloğu türlerinden biri kapsamdan çıktığında veya yok edildiğinde, otomatik olarak herhangi bir hedef bloktan bağlantısını keser. Bazı ileti bloğu türleri, yazabilmesi için en fazla hedef sayısını kısıtlar. Aşağıdaki bölümde, önceden tanımlı ileti bloğu türleri için uygulanan kısıtlamalar açıklanmaktadır.

[[Üst](#top)]

## <a name="overview-of-message-block-types"></a><a name="overview"></a> Ileti bloğu türlerine genel bakış

Aşağıdaki tablo, önemli ileti bloğu türlerinin rolünü kısaca açıklar.

[unbounded_buffer](#unbounded_buffer)<br/>
İleti kuyruğunu depolar.

[overwrite_buffer](#overwrite_buffer)<br/>
Yazılabilir bir ileti kaydeder ve birden çok kez okunabilir.

[single_assignment](#single_assignment)<br/>
Bir kez yazılabilen ve birden çok kez okunan bir iletiyi depolar.

[çaðýrmak](#call)<br/>
Bir ileti aldığında iş gerçekleştirir.

[dönüştürücü](#transformer)<br/>
Veri aldığında ve bu çalışmanın sonucunu başka bir hedef bloğa gönderdiğinde iş gerçekleştirir. `transformer`Sınıfı, farklı giriş ve çıkış türleri üzerinde işlem yapabilir.

[seçe](#choice)<br/>
Bir kaynak kümesinden ilk kullanılabilir iletiyi seçer.

[JOIN ve multitype JOIN](#join)<br/>
Bir kaynak kümesinden tüm iletilerin alınmasını bekleyin ve ardından iletileri başka bir ileti bloğu için tek bir iletiyle birleştirin.

[görevine](#timer)<br/>
Düzenli bir aralıktaki hedef bloğa bir ileti gönderir.

Bu ileti bloğu türleri, farklı durumlarda yararlı hale getirmek için farklı özelliklere sahiptir. Bunlar bazı özelliklerden bazılarıdır:

- *Yayma türü*: ileti bloğunun veri kaynağı, veri alıcısı veya her ikisi olarak hareket etmeyeceği.

- *İleti sıralaması*: ileti bloğunun, iletilerin gönderileceği veya alındığı orijinal sırayı korumasından bağımsız olup olmadığı. Her önceden tanımlı ileti bloğu türü, ileti gönderdiği veya aldığı orijinal sırayı korur.

- *Kaynak sayısı*: ileti bloğunun okuyabilen kaynak sayısı üst sınırı.

- *Hedef sayısı*: ileti bloğunun yazabileceği en fazla hedef sayısı.

Aşağıdaki tabloda, bu özelliklerin çeşitli ileti bloğu türleriyle ilgisi gösterilmektedir.

|İleti bloğu türü|Yayma türü (kaynak, hedef veya her Ikisi)|İleti sıralaması (sıralı veya sıralanmamış)|Kaynak sayısı|Hedef sayısı|
|------------------------|--------------------------------------------------|-----------------------------------------------|------------------|------------------|
|`unbounded_buffer`|Her ikisi|Sipariş edildi|Unbounded|Unbounded|
|`overwrite_buffer`|Her ikisi|Sipariş edildi|Unbounded|Unbounded|
|`single_assignment`|Her ikisi|Sipariş edildi|Unbounded|Unbounded|
|`call`|Hedef|Sipariş edildi|Unbounded|Geçerli değil|
|`transformer`|Her ikisi|Sipariş edildi|Unbounded|1|
|`choice`|Her ikisi|Sipariş edildi|10|1|
|`join`|Her ikisi|Sipariş edildi|Unbounded|1|
|`multitype_join`|Her ikisi|Sipariş edildi|10|1|
|`timer`|Kaynak|Geçerli değil|Geçerli değil|1|

Aşağıdaki bölümlerde ileti bloğu türleri daha ayrıntılı olarak açıklanır.

[[Üst](#top)]

## <a name="unbounded_buffer-class"></a><a name="unbounded_buffer"></a> unbounded_buffer sınıfı

[Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) sınıfı, genel amaçlı bir zaman uyumsuz mesajlaşma yapısını temsil eder. Bu sınıf, iletilerin birden çok kaynak tarafından yazılabilen veya birden çok hedef tarafından okunabilen bir ilk giren ilk çıkar (FIFO) sırasını tutar. Bir hedef bir nesneden bir ileti aldığında `unbounded_buffer` , bu ileti ileti sırasından kaldırılır. Bu nedenle, bir `unbounded_buffer` nesne birden çok hedef içerebilse de, her iletiyi yalnızca bir hedef alır. `unbounded_buffer` sınıfı, başka bir bileşene birden çok ileti geçirmek istediğinizde ve bu bileşenin her iletiyi alması gerektiğinde kullanışlıdır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir `unbounded_buffer` . Bu örnek, bir nesnesine üç değer gönderir `unbounded_buffer` ve ardından bu değerleri aynı nesneden geri okur.

[!code-cpp[concrt-unbounded_buffer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
334455
```

Sınıfının nasıl kullanılacağını gösteren bir örnek için `unbounded_buffer` bkz. [nasıl yapılır: çeşitli Producer-Consumer desenleri uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md).

[[Üst](#top)]

## <a name="overwrite_buffer-class"></a><a name="overwrite_buffer"></a> overwrite_buffer sınıfı

[Concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) sınıfı, bir `unbounded_buffer` `overwrite_buffer` nesnenin yalnızca bir ileti sakladığı durumlar dışında, sınıfa benzer. Ayrıca, bir hedef nesnesinden bir ileti aldığında `overwrite_buffer` , bu ileti arabellekten kaldırılmaz. Bu nedenle, birden çok hedef iletinin bir kopyasını alır.

`overwrite_buffer`Sınıfı, başka bir bileşene birden çok ileti geçirmek istediğinizde yararlıdır, ancak bu bileşen yalnızca en son değeri gerektirir. Bu sınıf, bir iletiyi birden çok bileşene yayınlamak istediğinizde de kullanışlıdır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir `overwrite_buffer` . Bu örnek, bir nesnesine üç değer gönderir `overwrite _buffer` ve ardından geçerli değeri üç kez aynı nesneden okur. Bu örnek, sınıfının örneğine benzerdir `unbounded_buffer` . Ancak, `overwrite_buffer` sınıfı yalnızca bir ileti depolar. Ayrıca, çalışma zamanı iletiyi, bir `overwrite_buffer` nesneden okunduktan sonra kaldırmaz.

[!code-cpp[concrt-overwrite_buffer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_2.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
555555
```

Sınıfının nasıl kullanılacağını gösteren bir örnek için `overwrite_buffer` bkz. [nasıl yapılır: çeşitli Producer-Consumer desenleri uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md).

[[Üst](#top)]

## <a name="single_assignment-class"></a><a name="single_assignment"></a> single_assignment sınıfı

[Concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) sınıfı, `overwrite_buffer` bir `single_assignment` nesnenin yalnızca bir kez yazılabilmesini hariç, sınıfa benzer. `overwrite_buffer` sınıfı gibi, hedef de bir `single_assignment` nesnesinden ileti aldığında, o ileti nesneden kaldırılmaz. Bu nedenle, birden çok hedef iletinin bir kopyasını alır. `single_assignment`Sınıfı, birden çok bileşene bir ileti yayınlamak istediğinizde faydalıdır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir `single_assignment` . Bu örnek, bir nesnesine üç değer gönderir `single_assignment` ve ardından geçerli değeri üç kez aynı nesneden okur. Bu örnek, sınıfının örneğine benzerdir `overwrite_buffer` . Hem hem de `overwrite_buffer` `single_assignment` sınıfları tek bir ileti deposa da, `single_assignment` sınıf yalnızca bir kez yazılabilir.

[!code-cpp[concrt-single_assignment-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_3.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
333333
```

Sınıfının nasıl kullanılacağını gösteren bir örnek için `single_assignment` bkz. [izlenecek yol: Işlem sürecini uygulama](../../parallel/concrt/walkthrough-implementing-futures.md).

[[Üst](#top)]

## <a name="call-class"></a><a name="call"></a> Call sınıfı

[Concurrency:: Call](../../parallel/concrt/reference/call-class.md) sınıfı, veri aldığında bir iş işlevi gerçekleştiren bir ileti alıcısı gibi davranır. Bu çalışma işlevi bir lambda ifadesi, bir işlev nesnesi veya bir işlev işaretçisi olabilir. Bir `call` nesne, kendisine ileti gönderen diğer bileşenlere paralel olarak davrandığı için sıradan işlev çağrısından farklı davranır. Bir `call` nesne bir ileti aldığında iş yapıyorsa, bu iletiyi bir kuyruğa ekler. Her `call` nesne, sıraya alınan iletileri alındıkları sırada işler.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir `call` . Bu örnek `call` , konsola aldığı her değeri yazdıran bir nesnesi oluşturur. Örnek daha sonra nesneye üç değer gönderir `call` . `call`Nesnesi ayrı bir iş parçacığında iletileri işlediğinden, bu örnek [](../../parallel/concrt/reference/event-class.md) Ayrıca `call` nesnenin `wmain` işlev dönüşden önce tüm iletileri işlediğinden emin olmak için bir sayaç değişkeni ve bir olay nesnesi kullanır.

[!code-cpp[concrt-call-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_4.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
334455
```

Sınıfının nasıl kullanılacağını gösteren bir örnek için `call` bkz. [nasıl yapılır: çağrı ve transformatör sınıflarına çalışma işlevleri sağlama](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md).

[[Üst](#top)]

## <a name="transformer-class"></a><a name="transformer"></a> Transformatör sınıfı

[Concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) sınıfı hem ileti alıcısı hem de ileti Gönderici olarak davranır. `transformer`Sınıfı, `call` veri aldığında Kullanıcı tanımlı bir iş işlevi gerçekleştirdiğinden sınıfına benzer. Ancak, `transformer` sınıfı iş işlevinin sonucunu alıcı nesnelerine de gönderir. Bir nesne gibi `call` , bir nesnesi `transformer` buna iletiler gönderen diğer bileşenlere paralel olarak davranır. Bir `transformer` nesne bir ileti aldığında iş yapıyorsa, bu iletiyi bir kuyruğa ekler. Her `transformer` nesne, sıraya alınan iletilerini alındıkları sırada işler.

`transformer`Sınıfı, iletisini bir hedefe gönderir. `_PTarget`Oluşturucusunda parametresini öğesine ayarlarsanız `NULL` , daha sonra [eşzamanlılık:: link_target](reference/source-block-class.md#link_target) yöntemini çağırarak hedefi belirtebilirsiniz.

Aracılar Kitaplığı tarafından belirtilen diğer tüm zaman uyumsuz ileti bloğu türlerinin aksine, `transformer` sınıfı farklı giriş ve çıkış türleri üzerinde işlem yapabilir. Verileri bir türden diğerine dönüştürebilme özelliği, `transformer` sınıfı birçok eşzamanlı ağda anahtar bileşen haline getirir. Buna ek olarak, bir nesnenin çalışma işlevine daha hassas paralel işlevler ekleyebilirsiniz `transformer` .

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir `transformer` . Bu örnek `transformer` , **`int`** çıkış olarak bir değer üretmek için her giriş değerini 0,33 ile çarpan bir nesne oluşturur **`double`** . Örnek daha sonra aynı nesneden dönüştürülen değerleri alır `transformer` ve bunları konsola yazdırır.

[!code-cpp[concrt-transformer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_5.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
10.8914.5218.15
```

Sınıfının nasıl kullanılacağını gösteren bir örnek için `transformer` bkz. [nasıl yapılır: bir veri ardışık düzeninde transformatör kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).

[[Üst](#top)]

## <a name="choice-class"></a><a name="choice"></a> seçim sınıfı

[Concurrency:: Choice](../../parallel/concrt/reference/choice-class.md) sınıfı bir kaynak kümesinden ilk kullanılabilir iletiyi seçer. `choice`Sınıfı, veri akışı mekanizması yerine bir denetim akışı mekanizmasını temsil eder ( [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) konusu veri akışı ile denetim akışı arasındaki farkları açıklar).

Seçim nesnesinden okuma, `WaitForMultipleObjects` `bWaitAll` parametresi olarak AYARLANDıĞıNDA Windows API işlevinin çağrılmasını benzerdir `FALSE` . Ancak, `choice` sınıfı verileri bir dış eşitleme nesnesi yerine olaya bağlar.

Genellikle, `choice` uygulamanızda denetim akışını sağlamak için [eşzamanlılık:: Receive](reference/concurrency-namespace-functions.md#receive) işleviyle birlikte sınıfını kullanırsınız. `choice`Farklı türlere sahip ileti arabellekleri arasından seçim yapmanız gerektiğinde sınıfını kullanın. `single_assignment`Aynı türde olan ileti arabelleklerinin arasından seçim yapmanız gerektiğinde sınıfını kullanın.

`choice`Hangi iletinin seçili olduğunu belirleyebildiğinden, kaynakları bir nesneye bağlama sırası önemlidir. Örneğin, zaten bir nesnesine ileti içeren birden çok ileti arabelleğini bağladığınızda oluşan durumu göz önünde bulundurun `choice` . `choice`Nesnesi, bağlandığı ilk kaynaktan iletiyi seçer. Tüm kaynakları bağlantıladıktan sonra, `choice` nesnesi her kaynağın bir ileti aldığı sırayı korur.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir `choice` . Bu örnek, üç ileti bloğu arasından seçim yapan bir nesne oluşturmak için [concurrency:: make_choice](reference/concurrency-namespace-functions.md#make_choice) işlevini kullanır `choice` . Örnek daha sonra çeşitli Fibonaccı numaralarını hesaplar ve her sonucu farklı bir ileti bloğunda depolar. Örnek daha sonra konsola önce tamamlanan işlemi temel alan bir ileti yazdırır.

[!code-cpp[concrt-choice-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_6.cpp)]

Bu örnek aşağıdaki örnek çıktıyı üretir:

```Output
fib35 received its value first. Result = 9227465
```

<sup>35.</sup> fibonaccı numarasını hesaplayan görevin, ilk başta tamamlanmayacağından, bu örneğin çıktısı farklılık gösterebilir.

Bu örnek, Fibonaccı numaralarını paralel olarak hesaplamak için [eşzamanlılık::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmasını kullanır. Hakkında daha fazla bilgi için `parallel_invoke` bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

Sınıfının nasıl kullanılacağını gösteren bir örnek için `choice` bkz. [nasıl yapılır: tamamlanan görevler arasında seçme](../../parallel/concrt/how-to-select-among-completed-tasks.md).

[[Üst](#top)]

## <a name="join-and-multitype_join-classes"></a><a name="join"></a> Sınıfları Birleştir ve multitype_join

[Concurrency:: JOIN](../../parallel/concrt/reference/join-class.md) ve [concurrency:: multitype_join](../../parallel/concrt/reference/multitype-join-class.md) sınıfları, bir kaynak kümesinin her bir üyesinin bir ileti almasını beklemenizi sağlar. `join`Sınıfı, ortak bir ileti türü olan kaynak nesneler üzerinde davranır. `multitype_join`Sınıfı, farklı ileti türlerine sahip olan kaynak nesneler üzerinde davranır.

Bir `join` veya nesnesinden okuma, `multitype_join` `WaitForMultipleObjects` `bWaitAll` PARAMETRESI olarak ayarlandığında Windows API işlevinin çağrılmasını benzerdir `TRUE` . Ancak, tıpkı bir `choice` nesnesi gibi `join` nesneler ve `multitype_join` nesneleri, verileri dış eşitleme nesnesi yerine olaya bağlayan bir olay mekanizması kullanır.

Bir nesneden okumak `join` std::[Vector](../../standard-library/vector-class.md) nesnesi oluşturur. Bir nesneden okumak `multitype_join` std::[Tuple](../../standard-library/tuple-class.md) nesnesi oluşturur. Öğeler, karşılık gelen kaynak arabelleklerine veya nesnesine bağlı olan bu nesnelerde aynı sırada görünür `join` `multitype_join` . Kaynak arabelleklerini bir veya nesnesine bağlamak için kullanılan sıra, `join` `multitype_join` sonuçta elde edilen ya da nesnedeki öğelerin sıralaması ile ilişkili olduğundan `vector` `tuple` , mevcut bir kaynak arabelleğinin bir birleşimden bağlantısını kaldırmanız önerilir. Bunun yapılması belirtilmeyen davranışa neden olabilir.

### <a name="greedy-versus-non-greedy-joins"></a>Doyumsuz Olmayan Birleştirmelere Karşı Doyumsuz

`join`Ve `multitype_join` sınıfları, doyumsuz ve doyumsuz olmayan birleştirmeler kavramını destekler. Bir *doyumsuz JOIN* , tüm iletiler kullanılabilir olana kadar iletiler kullanılabilir hale geldiğinde kaynaklarından her birinden bir ileti kabul eder. *Doyumsuz olmayan bir JOIN* iletileri iki aşamada alır. İlk olarak, doyumsuz olmayan bir JOIN, kaynaklarından her birinden bir ileti sunuluncaya kadar bekler. İkinci olarak, tüm kaynak iletileri kullanılabilir olduktan sonra, doyumsuz olmayan bir JOIN, bu mesajların her birini ayırmada çalışır. Her iletiyi ayırabiliyorsanız, tüm iletileri tüketir ve hedefine yayar. Aksi takdirde, ileti ayırmalarını serbest bırakır veya iptal eder, her kaynağın bir ileti almasını bekler.

Greedy birleştirmeleri, iletileri hemen kabul ettiğinden, doyumsuz olmayan birleştirmeleri daha iyi gerçekleştirir. Ancak, nadir durumlarda doyumsuz birleştirmeleri kilitlenmelere neden olabilir. Bir veya daha fazla paylaşılan kaynak nesnesi içeren birden çok birleşimleriniz olduğunda, greolmayan bir birleştirme kullanın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir `join` . Bu örnek, üç nesneden alan bir nesne oluşturmak için [concurrency:: make_join](reference/concurrency-namespace-functions.md#make_join) işlevini kullanır `join` `single_assignment` . Bu örnek, çeşitli Fibonaccı numaralarını hesaplar, her sonucu farklı bir `single_assignment` nesnede depolar ve sonra nesnenin tuttuğu her sonuç konsola yazdırır `join` . Bu örnek `choice` , sınıfının `join` tüm kaynak ileti bloklarının ileti almasını beklediği durumlar dışında, sınıfının örneğine benzerdir.

[!code-cpp[concrt-join-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_7.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
fib35 = 9227465fib37 = 24157817half_of_fib42 = 1.33957e+008
```

Bu örnek, Fibonaccı numaralarını paralel olarak hesaplamak için [eşzamanlılık::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmasını kullanır. Hakkında daha fazla bilgi için `parallel_invoke` bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

Sınıfının nasıl kullanılacağını gösteren tüm örnekler için `join` bkz. [nasıl yapılır: tamamlanan görevler arasında seçim](../../parallel/concrt/how-to-select-among-completed-tasks.md) yapma ve [Izlenecek yol: kilitlenmeyi engellemek için birleştirmeyi kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).

[[Üst](#top)]

## <a name="timer-class"></a><a name="timer"></a> Timer sınıfı

Concurrency::[Timer sınıfı](../../parallel/concrt/reference/timer-class.md) bir ileti kaynağı işlevi görür. Bir `timer` nesne, belirli bir süre geçtikten sonra hedefe bir ileti gönderir. `timer`Sınıfı, bir ileti göndermeyi geciktirmeli veya düzenli bir aralıkta ileti göndermek istediğinizde yararlıdır.

`timer`Sınıfı, iletisini yalnızca bir hedefe gönderir. `_PTarget`İçindeki parametresini öğesine ayarlarsanız `NULL` , daha sonra [concurrency:: ısource:: link_target](reference/source-block-class.md#link_target) yöntemini çağırarak hedefi belirtebilirsiniz.

Bir `timer` nesne tekrarveya tekrarsız olabilir. Yinelenen bir zamanlayıcı oluşturmak için, **`true`** `_Repeating` oluşturucuyu çağırdığınızda parametresini geçirin. Aksi takdirde, **`false`** `_Repeating` yineleme olmayan bir süreölçer oluşturmak için parametresini geçirin. Süreölçer tekraralıyorsa, her aralıktan sonra aynı iletiyi hedefine gönderir.

Aracılar Kitaplığı, `timer` başlatılmayan durumunda nesneler oluşturur. Bir Zamanlayıcı nesnesi başlatmak için [concurrency:: Timer:: Start](reference/timer-class.md#start) metodunu çağırın. Bir nesneyi durdurmak için `timer` , nesneyi yok edin veya [concurrency:: Timer:: stop](reference/timer-class.md#stop) metodunu çağırın. Yinelenen bir zamanlayıcıyı duraklatmak için [concurrency:: Timer::p ause](reference/timer-class.md#pause) metodunu çağırın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir `timer` . Bu örnek, `timer` `call` uzun bir işlemin ilerlemesini raporlamak için ve nesnelerini kullanır.

[!code-cpp[concrt-timer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_8.cpp)]

Bu örnek aşağıdaki örnek çıktıyı üretir:

```Output
Computing fib(42)..................................................result is 267914296
```

Sınıfının nasıl kullanılacağını gösteren bir örnek için `timer` , bkz. [nasıl yapılır: iletileri düzenli bir aralıkta gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md).

[[Üst](#top)]

## <a name="message-filtering"></a><a name="filtering"></a> İleti filtreleme

İleti bloğu nesnesi oluşturduğunuzda, ileti bloğunun bir iletiyi kabul edip etmediğini belirleyen bir *filtre işlevi* sağlayabilirsiniz. Filtre işlevi, ileti bloğunun yalnızca belirli değerleri almasını güvence altına almak için kullanışlı bir yoldur.

Aşağıdaki örnek, `unbounded_buffer` çift sayıları kabul etmek için bir filtre işlevi kullanan bir nesnenin nasıl oluşturulacağını gösterir. `unbounded_buffer`Nesne tek sayıları reddeder ve bu nedenle tek sayıları hedef bloklarına yayılmaz.

[!code-cpp[concrt-filter-function#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_9.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
0 2 4 6 8
```

Filtre işlevi bir Lambda işlevi, işlev işaretçisi veya işlev nesnesi olabilir. Her filtre işlevi aşağıdaki biçimlerden birini alır.

```Output
bool (T)
bool (T const &)
```

Verilerin gereksiz şekilde kopyalanmasını engellemek için, değere göre yayılan bir toplama türüne sahip olduğunuzda ikinci formu kullanın.

İleti filtrelemesi veri *akışı* programlama modelini destekler, bu da bileşenleri veri alırken hesaplamalar gerçekleştirir. Bir ileti geçirme ağı içindeki veri akışını denetlemek için filtre işlevlerini kullanan örnekler için bkz. [nasıl yapılır: Ileti bloğu filtresi kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md), [Izlenecek yol: veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)ve [Izlenecek yol: Image-Processing ağ oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).

[[Üst](#top)]

## <a name="message-reservation"></a><a name="reservation"></a> İleti ayırma

*İleti ayırma* bir ileti bloğunun daha sonra kullanılmak üzere bir ileti ayırmasını sağlar. Genellikle, ileti ayırma doğrudan kullanılmaz. Ancak, ileti ayırmayı anlamak, önceden tanımlanmış bazı ileti bloğu türlerinden bazılarının davranışını daha iyi anlamanıza yardımcı olabilir.

Greyumsuz ve doyumsuz birleştirmelerini göz önünde bulundurun. Bu her ikisi de daha sonra kullanılmak üzere ileti ayırmak için ileti ayırmayı kullanır. Daha önce açıklanan, doyumsuz olmayan bir birleşimde iletileri iki aşamada alır. İlk aşamada, doyumsuz olmayan bir `join` nesne, her birinin bir ileti almasını bekler. Doyumsuz olmayan bir JOIN, bu mesajların her birini ayırmasını dener. Her iletiyi ayırabiliyorsanız, tüm iletileri tüketir ve hedefine yayar. Aksi takdirde, ileti ayırmalarını serbest bırakır veya iptal eder, her kaynağın bir ileti almasını bekler.

Bir dizi kaynaktan gelen giriş iletilerini de okuyan doyumsuz JOIN, her kaynaktan bir ileti almak için beklediği sırada ek iletileri okumak için ileti ayırmayı kullanır. Örneğin ileti bloklarından ve iletileri alan doyumsuz JOIN 'i düşünün `A` `B` . Doyumsuz birleşimi, B 'den iki ileti alırsa ancak henüz öğesinden bir ileti almamışsa `A` doyumsuz JOIN, ikinci iletinin benzersiz ileti tanımlayıcısını ' den kaydeder `B` . Doyumsuz birleşimi öğesinden bir ileti aldıktan `A` ve bu iletileri yaydıktan sonra, ikinci iletinin kaynağından hala kullanılabilir olup olmadığını görmek için kaydedilen ileti tanımlayıcısını kullanır `B` .

Kendi özel ileti bloğu türlerinizi uyguladığınızda ileti ayırmayı kullanabilirsiniz. Özel ileti bloğu türü oluşturma hakkında bir örnek için bkz. [Izlenecek yol: özel bir Ileti bloğu oluşturma](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md).

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)
