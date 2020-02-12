---
title: Zaman Uyumsuz İleti Blokları
ms.date: 11/04/2016
helpviewer_keywords:
- non-greedy join [Concurrency Runtime]
- asynchronous message blocks
- greedy join [Concurrency Runtime]
ms.assetid: 79c456c0-1692-480c-bb67-98f2434c1252
ms.openlocfilehash: ef6f6f56a82cc76c2c270817ed40d15418960dc1
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141956"
---
# <a name="asynchronous-message-blocks"></a>Zaman Uyumsuz İleti Blokları

Aracılar Kitaplığı, iletileri iş parçacığı güvenli bir şekilde uygulama bileşenleri arasında yaymanızı sağlayan çeşitli ileti bloğu türleri sağlar. Bu ileti bloğu türleri genellikle [eşzamanlılık:: Send](reference/concurrency-namespace-functions.md#send), [concurrency:: asend](reference/concurrency-namespace-functions.md#asend), [concurrency:: receive](reference/concurrency-namespace-functions.md#receive)ve [concurrency:: try_receive](reference/concurrency-namespace-functions.md#try_receive)gibi çeşitli ileti geçirme yordamları ile kullanılır. Aracılar Kitaplığı tarafından tanımlanan yordamları geçirme hakkında daha fazla bilgi için bkz. [Ileti geçirme işlevleri](../../parallel/concrt/message-passing-functions.md).

## <a name="top"></a>Başlıklı

Bu konu aşağıdaki bölümleri içermektedir:

- [Kaynaklar ve hedefler](#sources_and_targets)

- [İleti yayma](#propagation)

- [Ileti bloğu türlerine genel bakış](#overview)

- [unbounded_buffer Sınıfı](#unbounded_buffer)

- [overwrite_buffer Sınıfı](#overwrite_buffer)

- [single_assignment Sınıfı](#single_assignment)

- [call Sınıfı](#call)

- [transformer Sınıfı](#transformer)

- [choice Sınıfı](#choice)

- [Sınıfları Birleştir ve multitype_join](#join)

- [timer Sınıfı](#timer)

- [İleti filtreleme](#filtering)

- [İleti ayırma](#reservation)

## <a name="sources_and_targets"></a>Kaynaklar ve hedefler

Kaynaklar ve hedefler ileti geçirme konusunda iki önemli katılımcılardır. *Kaynak* , ileti gönderen bir iletişim uç noktasını ifade eder. *Hedef* , iletileri alan bir iletişim uç noktası anlamına gelir. Bir kaynağı, yazdığınız bir uç nokta olarak ve bir hedefin üzerine yazdığınız bitiş noktası olarak düşünebilirsiniz. Uygulamalar, *mesajlaşma ağlarını*biçimlendirmek için kaynakları ve hedefleri birbirine bağlama.

Aracılar Kitaplığı, kaynakları ve hedefleri temsil etmek için iki soyut sınıf kullanır: [concurrency:: ISource](../../parallel/concrt/reference/isource-class.md) ve [concurrency:: itarget](../../parallel/concrt/reference/itarget-class.md). Kaynak olarak davranan ileti bloğu türleri `ISource`türetilir; hedef olarak davranan ileti bloğu türleri `ITarget`türetilir. Kaynak ve hedef gibi davranan ileti bloğu türleri hem `ISource` hem de `ITarget`türetilir.

[[Üst](#top)]

## <a name="propagation"></a>İleti yayma

*İleti yayma* , bir bileşenden diğerine ileti gönderme işlemidir. İleti bloğuna bir ileti sunulduğunda, bu iletiyi kabul edebilir, reddedebilir veya erteleyebilir. Her ileti bloğu türü, iletileri farklı yollarla depolar ve iletir. Örneğin, `unbounded_buffer` sınıfı sınırsız sayıda ileti depoladığında, `overwrite_buffer` sınıfı tek seferde tek bir ileti depolar ve transformatör sınıfı her iletinin değiştirilmiş bir sürümünü depolar. Bu ileti bloğu türleri bu belgenin ilerleyen bölümlerinde daha ayrıntılı açıklanmıştır.

İleti bloğu bir iletiyi kabul ettiğinde, isteğe bağlı olarak iş gerçekleştirebilir ve ileti bloğu bir kaynak ise, sonuç iletisini ağın başka bir üyesine geçirin. İleti bloğu, almasını istemediğiniz iletileri reddetmek için bir filtre işlevi kullanabilir. Filtreler, bu konunun ilerleyen bölümlerinde, [Ileti filtrelemesinde](#filtering)daha ayrıntılı bir şekilde açıklanmıştır. Bir iletiyi erteler bir ileti bloğu bu iletiyi ayırabilirler ve daha sonra tüketebilir. İleti ayırma, bu konunun ilerleyen kısımlarında, bölüm [Ileti ayırma](#reservation)bölümünde daha ayrıntılı olarak açıklanmıştır.

Aracılar Kitaplığı ileti bloklarının zaman uyumsuz veya zaman uyumlu olarak ileti geçişine olanak sağlar. İleti bloğuna eşzamanlı olarak ileti geçirdiğinizde, örneğin `send` işlevini kullanarak, hedef blok iletiyi kabul edene veya reddetene kadar çalışma zamanı geçerli bağlamı engeller. İleti bloğuna `asend` zaman uyumsuz olarak bir ileti geçirdiğinizde, çalışma zamanı iletiyi hedefe sağlar ve hedef iletiyi kabul ediyorsa, çalışma zamanı iletiyi alıcıya yayan bir zaman uyumsuz görevi zamanlar. Çalışma zamanı, iletileri birlikte bir şekilde yaymak için hafif görevler kullanır. Hafif görevler hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

Uygulamalar, mesajlaşma ağlarını biçimlendirmek için kaynakları ve hedefleri birbirine bağlama. Genellikle, ağa bağlanır ve verileri ağa geçirmek için `send` veya `asend` çağırın. Bir kaynak ileti bloğunu hedefe bağlamak için [concurrency:: ISource:: link_target](reference/isource-class.md#link_target) yöntemini çağırın. Kaynak bloğunun bir hedefle bağlantısını kesmek için [concurrency:: ISource:: unlink_target](reference/isource-class.md#unlink_target) yöntemini çağırın. Kaynak bloğunun tüm hedeflerinden bağlantısını kesmek için [eşzamanlılık:: ISource:: unlink_targets](reference/isource-class.md#unlink_targets) yöntemini çağırın. Önceden tanımlı ileti bloğu türlerinden biri kapsamdan çıktığında veya yok edildiğinde, otomatik olarak herhangi bir hedef bloktan bağlantısını keser. Bazı ileti bloğu türleri, yazabilmesi için en fazla hedef sayısını kısıtlar. Aşağıdaki bölümde, önceden tanımlı ileti bloğu türleri için uygulanan kısıtlamalar açıklanmaktadır.

[[Üst](#top)]

## <a name="overview"></a>Ileti bloğu türlerine genel bakış

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
Veri aldığında ve bu çalışmanın sonucunu başka bir hedef bloğa gönderdiğinde iş gerçekleştirir. `transformer` sınıfı, farklı giriş ve çıkış türleri üzerinde işlem yapabilir.

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
|`unbounded_buffer`|Her ikisi de|Sipariş edildi|Unbounded|Unbounded|
|`overwrite_buffer`|Her ikisi de|Sipariş edildi|Unbounded|Unbounded|
|`single_assignment`|Her ikisi de|Sipariş edildi|Unbounded|Unbounded|
|`call`|Hedef|Sipariş edildi|Unbounded|Uygulanamaz|
|`transformer`|Her ikisi de|Sipariş edildi|Unbounded|1\.|
|`choice`|Her ikisi de|Sipariş edildi|10|1\.|
|`join`|Her ikisi de|Sipariş edildi|Unbounded|1\.|
|`multitype_join`|Her ikisi de|Sipariş edildi|10|1\.|
|`timer`|Kaynak|Uygulanamaz|Uygulanamaz|1\.|

Aşağıdaki bölümlerde ileti bloğu türleri daha ayrıntılı olarak açıklanır.

[[Üst](#top)]

## <a name="unbounded_buffer"></a>unbounded_buffer sınıfı

[Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) sınıfı, genel amaçlı bir zaman uyumsuz mesajlaşma yapısını temsil eder. Bu sınıf, iletilerin birden çok kaynak tarafından yazılabilen veya birden çok hedef tarafından okunabilen bir ilk giren ilk çıkar (FIFO) sırasını tutar. Bir hedef `unbounded_buffer` nesnesinden bir ileti aldığında, bu ileti ileti sırasından kaldırılır. Bu nedenle, bir `unbounded_buffer` nesnesi birden çok hedef içerebilse de, her iletiyi yalnızca bir hedef alacaktır. `unbounded_buffer` sınıfı, başka bir bileşene birden çok ileti geçirmek istediğinizde ve bu bileşenin her iletiyi alması gerektiğinde kullanışlıdır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `unbounded_buffer` sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir. Bu örnek, `unbounded_buffer` nesnesine üç değer gönderir ve ardından bu değerleri aynı nesneden geri okur.

[!code-cpp[concrt-unbounded_buffer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
334455
```

`unbounded_buffer` sınıfının nasıl kullanılacağını gösteren tam bir örnek için bkz. [nasıl yapılır: çeşitli üretici-tüketici desenleri uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md).

[[Üst](#top)]

## <a name="overwrite_buffer"></a>overwrite_buffer sınıfı

[Concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) sınıfı, `unbounded_buffer` sınıfına benzer, ancak bir `overwrite_buffer` nesnesi yalnızca bir ileti depoladığından. Ayrıca, bir hedef `overwrite_buffer` nesnesinden bir ileti aldığında, bu ileti arabellekten kaldırılmaz. Bu nedenle, birden çok hedef iletinin bir kopyasını alır.

`overwrite_buffer` sınıfı, başka bir bileşene birden çok ileti geçirmek istediğinizde yararlıdır, ancak bu bileşen yalnızca en son değeri gerektirir. Bu sınıf, bir iletiyi birden çok bileşene yayınlamak istediğinizde de kullanışlıdır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `overwrite_buffer` sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir. Bu örnek, `overwrite _buffer` nesnesine üç değer gönderir ve ardından geçerli değeri üç kez aynı nesneden okur. Bu örnek, `unbounded_buffer` sınıfı için örneğe benzerdir. Ancak, `overwrite_buffer` sınıfı yalnızca bir ileti depolar. Ayrıca, çalışma zamanı, iletiyi, bir `overwrite_buffer` nesnesinden, okunduktan sonra kaldırmaz.

[!code-cpp[concrt-overwrite_buffer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_2.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
555555
```

`overwrite_buffer` sınıfının nasıl kullanılacağını gösteren tam bir örnek için bkz. [nasıl yapılır: çeşitli üretici-tüketici desenleri uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md).

[[Üst](#top)]

## <a name="single_assignment"></a>single_assignment sınıfı

[Concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) sınıfı `overwrite_buffer` sınıfına benzer, ancak bir `single_assignment` nesnesi yalnızca bir kez yazılabilirler. `overwrite_buffer` sınıfı gibi, hedef de bir `single_assignment` nesnesinden ileti aldığında, o ileti nesneden kaldırılmaz. Bu nedenle, birden çok hedef iletinin bir kopyasını alır. `single_assignment` sınıfı, birden çok bileşene bir ileti yayınlamak istediğinizde faydalıdır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `single_assignment` sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir. Bu örnek, `single_assignment` nesnesine üç değer gönderir ve ardından geçerli değeri üç kez aynı nesneden okur. Bu örnek, `overwrite_buffer` sınıfı için örneğe benzerdir. Hem `overwrite_buffer` hem de `single_assignment` sınıfları tek bir ileti depolasa da `single_assignment` sınıfı yalnızca bir kez yazılabilir.

[!code-cpp[concrt-single_assignment-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_3.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
333333
```

`single_assignment` sınıfının nasıl kullanılacağını gösteren bir örnek için bkz. [Izlenecek yol: Futures uygulama](../../parallel/concrt/walkthrough-implementing-futures.md).

[[Üst](#top)]

## <a name="call"></a>Call sınıfı

[Concurrency:: Call](../../parallel/concrt/reference/call-class.md) sınıfı, veri aldığında bir iş işlevi gerçekleştiren bir ileti alıcısı gibi davranır. Bu çalışma işlevi bir lambda ifadesi, bir işlev nesnesi veya bir işlev işaretçisi olabilir. `call` nesnesi, kendisine ileti gönderen diğer bileşenlere paralel olarak davrandığı için sıradan işlev çağrısından farklı davranır. Bir `call` nesnesi bir ileti aldığında iş yapıyorsa, bu iletiyi bir kuyruğa ekler. Her `call` nesnesi, sıraya alınan iletileri alındıkları sırada işler.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `call` sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir. Bu örnek, konsoluna aldığı her değeri yazdıran bir `call` nesnesi oluşturur. Örnek daha sonra `call` nesnesine üç değer gönderir. `call` nesnesi iletileri ayrı bir iş parçacığında işlediğinden, bu örnek ayrıca, `wmain` işlevi döndürülmadan önce `call` nesnesinin tüm iletileri işlediğinden emin olmak için bir sayaç değişkeni ve bir [olay](../../parallel/concrt/reference/event-class.md) nesnesi de kullanır.

[!code-cpp[concrt-call-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_4.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
334455
```

`call` sınıfının nasıl kullanılacağını gösteren bir örnek için bkz. [nasıl yapılır: çağrı ve transformatör sınıflarına çalışma Işlevleri sağlama](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md).

[[Üst](#top)]

## <a name="transformer"></a>Transformatör sınıfı

[Concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) sınıfı hem ileti alıcısı hem de ileti Gönderici olarak davranır. `transformer` sınıfı, veri aldığında Kullanıcı tanımlı bir iş işlevi gerçekleştirdiğinden `call` sınıfına benzer. Ancak, `transformer` sınıfı iş işlevinin sonucunu alıcı nesnelerine de gönderir. Bir `call` nesnesi gibi, bir `transformer` nesnesi buna ileti gönderen diğer bileşenlere paralel olarak davranır. Bir `transformer` nesnesi bir ileti aldığında iş yapıyorsa, bu iletiyi bir kuyruğa ekler. Her `transformer` nesnesi, sıraya alınan iletilerini alındıkları sırada işler.

`transformer` sınıfı, iletisini bir hedefe gönderir. Oluşturucuda `_PTarget` parametresini `NULL`olarak ayarlarsanız, daha sonra [concurrency:: link_target](reference/source-block-class.md#link_target) yöntemini çağırarak hedefi belirtebilirsiniz.

Aracılar Kitaplığı tarafından sunulan diğer tüm zaman uyumsuz ileti bloğu türlerinin aksine, `transformer` sınıfı farklı giriş ve çıkış türleri üzerinde işlem yapabilir. Verileri bir türden diğerine dönüştürebilme özelliği, `transformer` sınıfını birçok eşzamanlı ağlardaki anahtar bileşen haline getirir. Ayrıca, bir `transformer` nesnesinin çalışma işlevinde daha hassas paralel işlevler ekleyebilirsiniz.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `transformer` sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir. Bu örnek, çıkış olarak bir `double` değeri üretmek için her giriş `int` değerini 0,33 göre çarpan bir `transformer` nesnesi oluşturur. Örnek daha sonra aynı `transformer` nesnesinden dönüştürülen değerleri alır ve bunları konsola yazdırır.

[!code-cpp[concrt-transformer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_5.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
10.8914.5218.15
```

`transformer` sınıfının nasıl kullanılacağını gösteren bir örnek için bkz. [nasıl yapılır: bir veri ardışık düzeninde transformatör kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).

[[Üst](#top)]

## <a name="choice"></a>seçim sınıfı

[Concurrency:: Choice](../../parallel/concrt/reference/choice-class.md) sınıfı bir kaynak kümesinden ilk kullanılabilir iletiyi seçer. `choice` sınıfı, veri akışı mekanizması yerine bir denetim akışı mekanizmasını temsil eder ( [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) konusu veri akışı ile denetim akışı arasındaki farkları açıklar).

Seçim nesnesinden okuma, `bWaitAll` parametresi `FALSE`olarak ayarlandığında `WaitForMultipleObjects` Windows API işlevinin çağrılması benzerdir. Ancak `choice` sınıfı, verileri dış eşitleme nesnesi yerine olaya bağlar.

Genellikle, uygulamanızda denetim akışını yönlendirmek için `choice` sınıfını [eşzamanlılık:: Receive](reference/concurrency-namespace-functions.md#receive) işleviyle birlikte kullanırsınız. Farklı türlere sahip ileti arabelleklerinin arasından seçim yapmanız gerektiğinde `choice` sınıfını kullanın. Aynı türdeki ileti arabelleklerinin arasından seçim yapmanız gerektiğinde `single_assignment` sınıfını kullanın.

Hangi iletinin seçili olduğunu belirleyebildiğinden, kaynakları bir `choice` nesnesine bağlama sırası önemlidir. Örneğin, zaten bir `choice` nesnesine ileti içeren birden çok ileti arabelleğini bağladığınızda oluşan durumu göz önünde bulundurun. `choice` nesnesi, bağlandığı ilk kaynaktan iletiyi seçer. Tüm kaynakları bağlantıladıktan sonra, `choice` nesnesi her kaynağın bir ileti aldığı sırayı korur.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `choice` sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir. Bu örnek, üç ileti bloğu arasından seçim yapan bir `choice` nesnesi oluşturmak için [concurrency:: make_choice](reference/concurrency-namespace-functions.md#make_choice) işlevini kullanır. Örnek daha sonra çeşitli Fibonaccı numaralarını hesaplar ve her sonucu farklı bir ileti bloğunda depolar. Örnek daha sonra konsola önce tamamlanan işlemi temel alan bir ileti yazdırır.

[!code-cpp[concrt-choice-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_6.cpp)]

Bu örnek aşağıdaki örnek çıktıyı üretir:

```Output
fib35 received its value first. Result = 9227465
```

<sup>35.</sup> fibonaccı numarasını hesaplayan görevin, ilk başta tamamlanmayacağından, bu örneğin çıktısı farklılık gösterebilir.

Bu örnek, Fibonaccı numaralarını paralel olarak hesaplamak için [eşzamanlılık::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmasını kullanır. `parallel_invoke`hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

`choice` sınıfının nasıl kullanılacağını gösteren bir örnek için bkz. [nasıl yapılır: tamamlanan görevler arasında seçme](../../parallel/concrt/how-to-select-among-completed-tasks.md).

[[Üst](#top)]

## <a name="join"></a>Sınıfları Birleştir ve multitype_join

[Concurrency:: JOIN](../../parallel/concrt/reference/join-class.md) ve [concurrency:: multitype_join](../../parallel/concrt/reference/multitype-join-class.md) sınıfları, bir kaynak kümesinin her bir üyesinin bir ileti almasını beklemenizi sağlar. `join` sınıfı, ortak ileti türü olan kaynak nesneler üzerinde davranır. `multitype_join` sınıfı, farklı ileti türlerine sahip olabilir kaynak nesneleri üzerinde davranır.

Bir `join` veya `multitype_join` nesnesinden okuma, `bWaitAll` parametresi `TRUE`olarak ayarlandığında Windows API işlevi `WaitForMultipleObjects` çağırma ile benzerdir. Ancak, bir `choice` nesnesi gibi `join` ve `multitype_join` nesneleri, verileri dış eşitleme nesnesi yerine olaya bağlayan bir olay mekanizması kullanır.

Bir `join` nesnesinden okumak std::[Vector](../../standard-library/vector-class.md) nesnesi oluşturur. `multitype_join` nesnesinden okuma std::[Tuple](../../standard-library/tuple-class.md) nesnesi oluşturur. Öğeler, karşılık gelen kaynak arabelleklerinin `join` veya `multitype_join` nesnesine bağlandığı sırada bu nesnelerde görünür. Kaynak arabelleklerini bir `join` veya `multitype_join` nesnesine bağlama sırasındaki sıra, elde edilen `vector` veya `tuple` nesnesindeki öğelerin sıralaması ile ilişkili olduğundan, var olan bir kaynak arabelleğinin bir birleşimden bağlantısını kaldırmanız önerilir. Bunun yapılması belirtilmeyen davranışa neden olabilir.

### <a name="greedy-versus-non-greedy-joins"></a>Doyumsuz Olmayan Birleştirmelere Karşı Doyumsuz

`join` ve `multitype_join` sınıfları, doyumsuz ve doyumsuz olmayan birleştirmeler kavramını destekler. Bir *doyumsuz JOIN* , tüm iletiler kullanılabilir olana kadar iletiler kullanılabilir hale geldiğinde kaynaklarından her birinden bir ileti kabul eder. *Doyumsuz olmayan bir JOIN* iletileri iki aşamada alır. İlk olarak, doyumsuz olmayan bir JOIN, kaynaklarından her birinden bir ileti sunuluncaya kadar bekler. İkinci olarak, tüm kaynak iletileri kullanılabilir olduktan sonra, doyumsuz olmayan bir JOIN, bu mesajların her birini ayırmada çalışır. Her iletiyi ayırabiliyorsanız, tüm iletileri tüketir ve hedefine yayar. Aksi takdirde, ileti ayırmalarını serbest bırakır veya iptal eder, her kaynağın bir ileti almasını bekler.

Greedy birleştirmeleri, iletileri hemen kabul ettiğinden, doyumsuz olmayan birleştirmeleri daha iyi gerçekleştirir. Ancak, nadir durumlarda doyumsuz birleştirmeleri kilitlenmelere neden olabilir. Bir veya daha fazla paylaşılan kaynak nesnesi içeren birden çok birleşimleriniz olduğunda, greolmayan bir birleştirme kullanın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `join` sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir. Bu örnek, üç `single_assignment` nesnesinden alan bir `join` nesnesi oluşturmak için [concurrency:: make_join](reference/concurrency-namespace-functions.md#make_join) işlevini kullanır. Bu örnek, çeşitli Fibonaccı numaralarını hesaplar, her sonucu farklı bir `single_assignment` nesnesi halinde depolar ve sonra `join` nesnesinin tuttuğu her sonuç konsola yazdırır. Bu örnek, `join` sınıfının tüm kaynak ileti bloklarının ileti almasını beklediği durumlar dışında, `choice` sınıfı için örneğe benzerdir.

[!code-cpp[concrt-join-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_7.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
fib35 = 9227465fib37 = 24157817half_of_fib42 = 1.33957e+008
```

Bu örnek, Fibonaccı numaralarını paralel olarak hesaplamak için [eşzamanlılık::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmasını kullanır. `parallel_invoke`hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

`join` sınıfının nasıl kullanılacağını gösteren tüm örnekler için bkz. [nasıl yapılır: tamamlanan görevler arasında seçim](../../parallel/concrt/how-to-select-among-completed-tasks.md) yapma ve [Izlenecek yol: kilitlenmeyi engellemek için birleştirmeyi kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).

[[Üst](#top)]

## <a name="timer"></a>Timer sınıfı

Concurrency::[Timer sınıfı](../../parallel/concrt/reference/timer-class.md) bir ileti kaynağı işlevi görür. `timer` nesnesi, belirli bir süre geçtikten sonra hedefe bir ileti gönderir. `timer` sınıfı, bir ileti göndermeyi geciktirmeli veya düzenli bir aralıkta ileti göndermek istediğinizde yararlıdır.

`timer` sınıfı iletisi yalnızca bir hedefe gönderilir. Oluşturucuda `_PTarget` parametresini `NULL`olarak ayarlarsanız, daha sonra [concurrency:: ISource:: link_target](reference/source-block-class.md#link_target) metodunu çağırarak hedefi belirtebilirsiniz.

`timer` nesne tekrarveya tekrarsız olabilir. Yinelenen bir zamanlayıcı oluşturmak için, oluşturucuyu çağırdığınızda `_Repeating` parametresi için **true** geçirin. Aksi takdirde, yinelenmeyen bir zamanlayıcı oluşturmak için `_Repeating` parametresi için **false** geçirin. Süreölçer tekraralıyorsa, her aralıktan sonra aynı iletiyi hedefine gönderir.

Aracılar Kitaplığı, başlatılmamış durumda `timer` nesneleri oluşturur. Bir Zamanlayıcı nesnesi başlatmak için [concurrency:: Timer:: Start](reference/timer-class.md#start) metodunu çağırın. `timer` nesnesini durdurmak için, nesneyi yok edin veya [concurrency:: Timer:: stop](reference/timer-class.md#stop) metodunu çağırın. Yinelenen bir zamanlayıcıyı duraklatmak için [concurrency:: Timer::p ause](reference/timer-class.md#pause) metodunu çağırın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `timer` sınıfıyla nasıl çalışacağınıza ilişkin temel yapıyı gösterir. Örnek, uzun bir işlemin ilerlemesini raporlamak için `timer` ve `call` nesnelerini kullanır.

[!code-cpp[concrt-timer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_8.cpp)]

Bu örnek aşağıdaki örnek çıktıyı üretir:

```Output
Computing fib(42)..................................................result is 267914296
```

`timer` sınıfının nasıl kullanılacağını gösteren bir örnek için, bkz. [nasıl yapılır: Iletileri düzenli bir aralıkta gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md).

[[Üst](#top)]

## <a name="filtering"></a>İleti filtreleme

İleti bloğu nesnesi oluşturduğunuzda, ileti bloğunun bir iletiyi kabul edip etmediğini belirleyen bir *filtre işlevi* sağlayabilirsiniz. Filtre işlevi, ileti bloğunun yalnızca belirli değerleri almasını güvence altına almak için kullanışlı bir yoldur.

Aşağıdaki örnek, çift sayıları kabul etmek için bir filtre işlevi kullanan bir `unbounded_buffer` nesnesinin nasıl oluşturulacağını gösterir. `unbounded_buffer` nesnesi tek sayıları reddeder ve bu nedenle tek sayıları hedef bloklarına yayılmaz.

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

İleti filtrelemesi veri *akışı* programlama modelini destekler, bu da bileşenleri veri alırken hesaplamalar gerçekleştirir. Bir ileti geçirme ağı içindeki veri akışını denetlemek için filtre işlevlerini kullanan örnekler için bkz. [nasıl yapılır: Ileti bloğu filtresi kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md), [Izlenecek yol: veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)ve [Izlenecek yol: görüntü işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).

[[Üst](#top)]

## <a name="reservation"></a>İleti ayırma

*İleti ayırma* bir ileti bloğunun daha sonra kullanılmak üzere bir ileti ayırmasını sağlar. Genellikle, ileti ayırma doğrudan kullanılmaz. Ancak, ileti ayırmayı anlamak, önceden tanımlanmış bazı ileti bloğu türlerinden bazılarının davranışını daha iyi anlamanıza yardımcı olabilir.

Greyumsuz ve doyumsuz birleştirmelerini göz önünde bulundurun. Bu her ikisi de daha sonra kullanılmak üzere ileti ayırmak için ileti ayırmayı kullanır. Daha önce açıklanan, doyumsuz olmayan bir birleşimde iletileri iki aşamada alır. İlk aşamada, doyumsuz olmayan `join` bir nesne, her birinin bir ileti almasını bekler. Doyumsuz olmayan bir JOIN, bu mesajların her birini ayırmasını dener. Her iletiyi ayırabiliyorsanız, tüm iletileri tüketir ve hedefine yayar. Aksi takdirde, ileti ayırmalarını serbest bırakır veya iptal eder, her kaynağın bir ileti almasını bekler.

Bir dizi kaynaktan gelen giriş iletilerini de okuyan doyumsuz JOIN, her kaynaktan bir ileti almak için beklediği sırada ek iletileri okumak için ileti ayırmayı kullanır. Örneğin, ileti bloklarında `A` ve `B`ileti alan doyumsuz JOIN 'i düşünün. Doyumsuz birleşimi B 'den iki ileti alırsa ancak henüz `A`bir ileti almamışsa doyumsuz birleşimi, `B`ikinci iletinin benzersiz ileti tanımlayıcısını kaydeder. Doyumsuz birleşimi `A` 'den bir ileti aldıktan ve bu iletileri yaydıktan sonra, `B` ikinci iletinin hala kullanılabilir olup olmadığını görmek için kaydedilmiş ileti tanımlayıcısını kullanır.

Kendi özel ileti bloğu türlerinizi uyguladığınızda ileti ayırmayı kullanabilirsiniz. Özel ileti bloğu türü oluşturma hakkında bir örnek için bkz. [Izlenecek yol: özel bir Ileti bloğu oluşturma](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md).

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)
