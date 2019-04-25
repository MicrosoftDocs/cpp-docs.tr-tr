---
title: Zaman Uyumsuz İleti Blokları
ms.date: 11/04/2016
helpviewer_keywords:
- non-greedy join [Concurrency Runtime]
- asynchronous message blocks
- greedy join [Concurrency Runtime]
ms.assetid: 79c456c0-1692-480c-bb67-98f2434c1252
ms.openlocfilehash: de6a433ab733207d5c56b46e693837056a0cd8b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237083"
---
# <a name="asynchronous-message-blocks"></a>Zaman Uyumsuz İleti Blokları

Agents kitaplığı, uygulama bileşenleri arasında iletileri iş parçacığı açısından güvenli bir şekilde yayılmasına olanak sağlayan birkaç ileti bloğu türü sağlar. Bu ileti bloğu türleri genellikle çeşitli ileti geçirme yordamları gibi kullanılan [concurrency::send](reference/concurrency-namespace-functions.md#send), [concurrency::asend](reference/concurrency-namespace-functions.md#asend), [concurrency::receive](reference/concurrency-namespace-functions.md#receive), ve [concurrency::try_receive](reference/concurrency-namespace-functions.md#try_receive). İleti Aracılar Kitaplığı tarafından tanımlanan yordamları geçirme hakkında daha fazla bilgi için bkz: [ileti geçirme işlevleri](../../parallel/concrt/message-passing-functions.md).

##  <a name="top"></a> Bölümleri

Bu konu aşağıdaki bölümleri içermektedir:

- [Kaynaklar ve hedefler](#sources_and_targets)

- [İleti yayma](#propagation)

- [İleti bloğu türlerine genel bakış](#overview)

- [unbounded_buffer Sınıfı](#unbounded_buffer)

- [overwrite_buffer Sınıfı](#overwrite_buffer)

- [single_assignment Sınıfı](#single_assignment)

- [call Sınıfı](#call)

- [transformer Sınıfı](#transformer)

- [choice Sınıfı](#choice)

- [birleştirme ve multitype_join sınıfları](#join)

- [timer Sınıfı](#timer)

- [İleti filtreleme](#filtering)

- [İleti rezervasyonu](#reservation)

##  <a name="sources_and_targets"></a> Kaynaklar ve hedefler

Kaynaklar ve hedefler, ileti geçirme iki önemli katılımcıları olan. A *kaynak* bir uç noktaya iletileri gönderen iletişimi ifade eder. A *hedef* bir uç noktaya iletileri alan iletişimi ifade eder. Okuma bir uç nokta olarak bir kaynak ve hedef için yazdığınız bir uç nokta olarak düşünebilirsiniz. Uygulamaları, forma kaynaklar ve hedefler birbirine bağlama *ağları Mesajlaşma*.

Agents kitaplığı, kaynakları ve hedefleri temsil etmek için iki soyut sınıflar kullanır: [CONCURRENCY::ısource](../../parallel/concrt/reference/isource-class.md) ve [CONCURRENCY::ıtarget](../../parallel/concrt/reference/itarget-class.md). Kaynakları türetilmesi gibi davranan ileti bloğu türleri `ISource`; hedefleri türetilmesi gibi davranan ileti bloğu türleri `ITarget`. İleti bloğu türleri davranan kaynakları ve hedefleri hem türetilen `ISource` ve `ITarget`.

[[Üst](#top)]

##  <a name="propagation"></a> İleti yayma

*İleti yayılımını* bir bileşenden bir ileti gönderme işlemidir. Bir ileti bloğu bir ileti sunulduğunda bunu kabul, reddetme veya bu iletiyi erteleyebilir. Her bir mesaj engelleme türü depolar ve farklı şekillerde iletileri aktarır. Örneğin, `unbounded_buffer` sınıfı iletileri, sınırsız sayıda depolar `overwrite_buffer` sınıfı, bir kerede tek bir ileti depolar ve her iletinin değiştirilmiş bir sürümünü transformer sınıfını depolar. Bu ileti bloğu türleri bu belgenin ilerleyen bölümlerinde daha ayrıntılı açıklanmıştır.

Bir ileti bloğu iletiyi kabul ettiğinde, isteğe bağlı olarak çalışma gerçekleştirme ve, ileti bloğu bir kaynak olup olmadığını elde edilen ileti ağ başka bir üyesi geçirin. Bir ileti bloğu almaya istemediği iletileri reddetmek için bir filtre işlevi kullanabilirsiniz. Filtreleri bölümünde bu konunun ilerleyen bölümlerinde daha ayrıntılı açıklanmıştır [ileti filtreleme](#filtering). İletiyi erteleyen bir ileti bloğu bu iletiyi ayırabilir ve daha sonra kullanma. İleti rezervasyonu bölümünde bu konunun ilerleyen bölümlerinde daha ayrıntılı açıklanmıştır [ileti rezervasyonlarına](#reservation).

Agents kitaplığı, ileti bloklarına zaman uyumsuz olarak etkinleştirir veya iletileri eşzamanlı olarak geçirin. Gönderdiğinizde ileti bir ileti bloğu için zaman uyumlu olarak, örneğin, kullanarak `send` işlevi, çalışma zamanı geçerli bağlam hedef blok kabul veya iletiyi reddettiğinde kadar engeller. Gönderdiğinizde ileti bir ileti bloğu için zaman uyumsuz olarak örneğin kullanarak `asend` işlevi, çalışma zamanı hedefe bir ileti sunar ve hedef iletiyi kabul ederse, çalışma zamanı iletiyi yayar, zaman uyumsuz bir görevi zamanlar. Alıcı için. Çalışma zamanı Basit görevler çalışılabilir bir ileti yaymak için kullanır. Basit görevler hakkında daha fazla bilgi için bkz: [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

Uygulamaları kaynaklar ve hedefler birlikte ileti biçimine bağlayın. Genellikle, arama ve ağ bağlantısını `send` veya `asend` ağa veri iletmek için. Bir hedef kaynak ileti bloğu bağlanmak için çağrı [concurrency::ISource::link_target](reference/isource-class.md#link_target) yöntemi. Hedef kaynak blok kesmek için çağrı [concurrency::ISource::unlink_target](reference/isource-class.md#unlink_target) yöntemi. Bir kaynak blok tüm hedeflerine bağlantıyı kesmek için çağrı [concurrency::ISource::unlink_targets](reference/isource-class.md#unlink_targets) yöntemi. Önceden tanımlanmış bir ileti bloğu türleri birini kapsam dışına çıktığında veya kaldırıldığı zaman bunu otomatik olarak kendisini herhangi bir hedef bloğu bağlantısını keser. Bazı ileti bloğu türleri için yazabilirsiniz hedefleri sayısını kısıtlayın. Aşağıdaki bölümde, önceden tanımlanmış ileti bloğu türleri için uygulanan kısıtlamaları açıklamaktadır.

[[Üst](#top)]

##  <a name="overview"></a> İleti bloğu türlerine genel bakış

Aşağıdaki tabloda, önemli bir ileti bloğu türleri rolü kısaca açıklanmaktadır.

[unbounded_buffer](#unbounded_buffer)<br/>
Bir kuyruk iletilerinin depolar.

[overwrite_buffer](#overwrite_buffer)<br/>
Yazılan ve birden çok kez okuma bir iletiyi depolar.

[single_assignment](#single_assignment)<br/>
Bir kez yazıldığı ve birden çok kez okuma bir iletiyi depolar.

[Çağrı](#call)<br/>
Bir ileti aldığında, çalışma gerçekleştirir.

[Transformer](#transformer)<br/>
Verileri alır ve bu iş sonucu başka bir hedef bloğa gönderir çalışma gerçekleştirir. `transformer` Farklı giriş ve çıkış türü sınıf hareket edebilir.

[Seçim](#choice)<br/>
Kullanılabilir ilk iletinin, kaynaklarına kümesinden seçer.

[katılma ve multitype birleştirme](#join)<br/>
Başka bir ileti bloğu için bir ileti iletileri birleştirin ve kaynakları kümesinden alınabilmesi tüm iletiler için bekleyin.

[Zamanlayıcı](#timer)<br/>
Bir ileti hedef bloğa düzenli aralıklarla gönderir.

Bu ileti bloğu türleri farklı durumlar için yararlı hale farklı özelliklere sahiptir. Bu özelliklerin bazıları şunlardır:

- *Yayma türü*: Olup ileti bloğu verileri, verilerin bir alıcı veya ikisinin bir kaynak olarak davranır.

- *Mesaj sıralama*: Olup ileti bloğu iletileri gönderilen veya alınan özgün sırasını korur. Her önceden tanımlı bir ileti bloğu türü olan gönderdiğinde veya ileti aldığında özgün sırasını korur.

- *Kaynak sayısı*: İleti bloğu okuyabileceği kaynakları maksimum sayısı.

- *Hedef sayısının*: İleti bloğu yazabilirsiniz hedefleri maksimum sayısı.

Aşağıdaki tabloda, bu özellikleri için çeşitli ileti bloğu türleri nasıl ilişkili olduğunu gösterir.

|Mesaj engelleme türü|Yayma türü (kaynak, hedef veya her ikisi de)|Mesaj sıralama sistemi (sipariş edilmiş veya Unordered)|Kaynak sayısı|Hedef sayısı|
|------------------------|--------------------------------------------------|-----------------------------------------------|------------------|------------------|
|`unbounded_buffer`|Her ikisi de|Sıralı|sınırsız|sınırsız|
|`overwrite_buffer`|Her ikisi de|Sıralı|sınırsız|sınırsız|
|`single_assignment`|Her ikisi de|Sıralı|sınırsız|sınırsız|
|`call`|Hedef|Sıralı|sınırsız|Uygulanamaz|
|`transformer`|Her ikisi de|Sıralı|sınırsız|1.|
|`choice`|Her ikisi de|Sıralı|10|1.|
|`join`|Her ikisi de|Sıralı|sınırsız|1.|
|`multitype_join`|Her ikisi de|Sıralı|10|1.|
|`timer`|Source|Uygulanamaz|Uygulanamaz|1.|

Aşağıdaki bölümlerde daha ayrıntılı ileti bloğu türleri açıklanmaktadır.

[[Üst](#top)]

##  <a name="unbounded_buffer"></a> unbounded_buffer sınıfı

[Concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) sınıfı, genel amaçlı bir zaman uyumsuz ileti yapısını temsil eder. Bu sınıf, iletilerin birden çok kaynak tarafından yazılabilen veya birden çok hedef tarafından okunabilen bir ilk giren ilk çıkar (FIFO) sırasını tutar. Bir hedefe bir ileti aldığında bir `unbounded_buffer` nesnesi, bu iletiyi, ileti sırasından kaldırılır. Bu nedenle, ancak bir `unbounded_buffer` nesne birden çok hedefe sahip olabilir, her ileti yalnızca bir hedef alır. `unbounded_buffer` sınıfı, başka bir bileşene birden çok ileti geçirmek istediğinizde ve bu bileşenin her iletiyi alması gerektiğinde kullanışlıdır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, temel yapısı ile nasıl çalışılacağını gösterir `unbounded_buffer` sınıfı. Bu örnek, üç değerlere gönderir. bir `unbounded_buffer` nesnesi ve ardından bu değerleri aynı nesneden geri okur.

[!code-cpp[concrt-unbounded_buffer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
334455
```

Nasıl kullanılacağını gösteren tam bir örnek `unbounded_buffer` sınıfı [nasıl yapılır: Çeşitli üretici-tüketici desenlerini uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md).

[[Üst](#top)]

##  <a name="overwrite_buffer"></a> overwrite_buffer sınıfı

[Concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) sınıfına benzer `unbounded_buffer` ancak bir `overwrite_buffer` nesnesi yalnızca bir ileti kaydeder. Ayrıca, bir hedef aldığında bir iletiyi sıradan bir `overwrite_buffer` nesnesi, o ileti arabellek kaldırılmaz. Bu nedenle, birden çok hedef iletinin bir kopyasını alır.

`overwrite_buffer` Sınıfı, başka bir bileşene birden çok ileti geçirmek istediğiniz, ancak söz konusu bileşen'ı yalnızca en son değeri okuması gerektiğinde kullanışlıdır. Bu sınıf, bir iletiyi birden çok bileşene yayınlamak istediğinizde de kullanışlıdır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, temel yapısı ile nasıl çalışılacağını gösterir `overwrite_buffer` sınıfı. Bu örnek, üç değerlere gönderir. bir `overwrite _buffer` nesne ve geçerli değerini üç kez aynı nesneden okur. Bu örnek için örneğe benzer `unbounded_buffer` sınıfı. Ancak, `overwrite_buffer` sınıfı yalnızca bir iletiyi depolar. Ayrıca, çalışma zamanı iletiden kaldırmaz bir `overwrite_buffer` okunur sonra nesne.

[!code-cpp[concrt-overwrite_buffer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_2.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
555555
```

Nasıl kullanılacağını gösteren tam bir örnek `overwrite_buffer` sınıfı [nasıl yapılır: Çeşitli üretici-tüketici desenlerini uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md).

[[Üst](#top)]

##  <a name="single_assignment"></a> single_assignment sınıfı

[Concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) sınıfına benzer `overwrite_buffer` ancak bir `single_assignment` nesne yalnızca bir kez yazılabilir. `overwrite_buffer` sınıfı gibi, hedef de bir `single_assignment` nesnesinden ileti aldığında, o ileti nesneden kaldırılmaz. Bu nedenle, birden çok hedef iletinin bir kopyasını alır. `single_assignment` Sınıfı, bir iletiyi birden çok bileşene yayınlamak istediğinizde yararlıdır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, temel yapısı ile nasıl çalışılacağını gösterir `single_assignment` sınıfı. Bu örnek, üç değerlere gönderir. bir `single_assignment` nesne ve geçerli değerini üç kez aynı nesneden okur. Bu örnek için örneğe benzer `overwrite_buffer` sınıfı. Olsa da hem `overwrite_buffer` ve `single_assignment` sınıfları depolamak tek bir ileti `single_assignment` sınıfı yalnızca bir kez yazılabilir.

[!code-cpp[concrt-single_assignment-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_3.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
333333
```

Nasıl kullanılacağını gösteren tam bir örnek `single_assignment` sınıfı [izlenecek yol: Vadeli işlemleri uygulama](../../parallel/concrt/walkthrough-implementing-futures.md).

[[Üst](#top)]

##  <a name="call"></a> Çağrı sınıfı

[Concurrency::call](../../parallel/concrt/reference/call-class.md) veri aldığında, bir iş işlevi gerçekleştiren bir ileti alıcısı sınıf görevi görür. Bu iş işlevi lambda ifadesi, bir işlev nesnesi veya bir işlev işaretçisi olabilir. A `call` nesne davranışını bir normal işlev çağrısı farklı bileşenlerle iletileri göndermek için paralel karıncaların. Varsa bir `call` nesnesi bir ileti aldığı zaman iş gerçekleştirmeden, bu iletiyi bir kuyruğa ekler. Her `call` nesne işlemleri bunlar alınan sırası iletileri kuyruğa alındı.

### <a name="example"></a>Örnek

Aşağıdaki örnek, temel yapısı ile nasıl çalışılacağını gösterir `call` sınıfı. Bu örnekte bir `call` konsola alan her değerin yazdırır nesne. Örnek, ardından üç değerlere gönderir `call` nesne. Çünkü `call` iletileri ayrı bir iş parçacığında nesnesini işler, bu örnek, bir sayaç değişkeni de kullanır ve bir [olay](../../parallel/concrt/reference/event-class.md) emin olmak için nesne `call` nesne önce tüm iletileri işleyen `wmain` işlev döndürür.

[!code-cpp[concrt-call-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_4.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
334455
```

Nasıl kullanılacağını gösteren tam bir örnek `call` sınıfı [nasıl yapılır: Call ve transformer sınıflarına iş işlevleri sağlama](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md).

[[Üst](#top)]

##  <a name="transformer"></a> Transformer sınıfı

[Concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) sınıfı davranır ve iletiyi gönderen her iki ileti alıcısı olarak. `transformer` Sınıfına benzer `call` veri aldığında bir kullanıcı tarafından tanımlanan iş işlevini gerçekleştirdiğinden sınıfı. Ancak, `transformer` sınıfı ayrıca iş işlevin sonucu alıcı nesnelere gönderir. Gibi bir `call` nesnesi bir `transformer` nesne işlevi görür paralel olarak göndermek için diğer bileşenleri. Varsa bir `transformer` nesnesi bir ileti aldığı zaman iş gerçekleştirmeden, bu iletiyi bir kuyruğa ekler. Her `transformer` nesnesini kullanıcıdan aldığı sırada, sıraya alınan iletileri işler.

`transformer` Sınıfı için bir hedef, ileti gönderir. Ayarlarsanız `_PTarget` oluşturucuda parametre `NULL`, daha sonra hedef çağırarak belirtebileceğiniz [concurrency::link_target](reference/source-block-class.md#link_target) yöntemi.

Aracılar Kitaplığı tarafından sağlanan tüm diğer zaman uyumsuz ileti bloğu türleri farklı `transformer` farklı giriş ve çıkış türü sınıf hareket edebilir. Bu özelliği başka bir hale gelmesi için verileri bir türden diğerine dönüştürme `transformer` temel bir bileşeni çok sayıda eş zamanlı ağlardaki sınıfı. Ayrıca, daha fazla ayrıntılı paralel işlevler çalışma işlevi ekleyebilirsiniz bir `transformer` nesne.

### <a name="example"></a>Örnek

Aşağıdaki örnek, temel yapısı ile nasıl çalışılacağını gösterir `transformer` sınıfı. Bu örnekte bir `transformer` katları her giriş nesnesi `int` değeri üretmek için 0.33 tarafından bir `double` çıktı olarak değeri. Örnek ardından dönüştürülen değerler aynı alan `transformer` nesne ve bunları konsola yazdırır.

[!code-cpp[concrt-transformer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_5.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
10.8914.5218.15
```

Nasıl kullanılacağını gösteren tam bir örnek `transformer` sınıfı [nasıl yapılır: Veri ardışık düzeninde transformer kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).

[[Üst](#top)]

##  <a name="choice"></a> choice sınıfı

[Concurrency::choice](../../parallel/concrt/reference/choice-class.md) sınıf kaynakları kümesinden ilk kullanılabilir ileti seçer. `choice` Sınıfı, bir veri akışı mekanizması yerine bir akış denetimi mekanizmasını temsil eder (konu [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) veri akışı ve denetim akışı arasındaki farklar açıklanmaktadır).

Bir seçim nesnesinden okuma benzer Windows API işlevi çağırma `WaitForMultipleObjects` sahip olduğunda `bWaitAll` parametresini `FALSE`. Ancak, `choice` sınıfı, bir dış eşitleme nesnesi için olay yerine veri bağlar.

Genellikle, kullandığınız `choice` ile birlikte sınıfı [concurrency::receive](reference/concurrency-namespace-functions.md#receive) uygulamanızda denetim akışı sürücü için işlevi. Kullanım `choice` sınıfı, farklı türlere sahip ileti arabelleklerinin seçmeniz gerektiğinde. Kullanım `single_assignment` sınıfı, aynı türe sahip ileti arabelleklerinin seçmeniz gerektiğinde.

Kaynaklarına bağlama sırası bir `choice` ileti seçili belirleyebilirsiniz çünkü nesne önemlidir. Örneğin, zaten bir ileti içeren birden çok ileti arabelleklerinin bağlantı olduğu bir durum düşünün bir `choice` nesne. `choice` Nesne bağlı olduğu ilk kaynak ileti seçer. Tüm kaynakları bağladıktan sonra `choice` nesnesi, her kaynak bir ileti alır sırasını korur.

### <a name="example"></a>Örnek

Aşağıdaki örnek, temel yapısı ile nasıl çalışılacağını gösterir `choice` sınıfı. Bu örnekte [concurrency::make_choice](reference/concurrency-namespace-functions.md#make_choice) oluşturmak için işlevi bir `choice` üç ileti blokları seçen bir nesne. Örnek çeşitli Fibonacci numaraları hesaplar ve her sonucu farklı bir ileti bloğu içinde depolar. Örneğin, ardından önce tamamlanmış işleme bağlı bir ileti konsola yazdırır.

[!code-cpp[concrt-choice-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_6.cpp)]

Bu örnek, örnek aşağıdaki çıktıyı üretir:

```Output
fib35 received its value first. Result = 9227465
```

Çünkü 35 hesaplar görev<sup>th</sup> Fibonacci numarası ilk olarak garanti edilmez, bu örnek çıktısı farklılık gösterebilir.

Bu örnekte [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) paralel Fibonacci sayıları hesaplamak için kullanılan algoritma. Hakkında daha fazla bilgi için `parallel_invoke`, bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

Nasıl kullanılacağını gösteren tam bir örnek `choice` sınıfı [nasıl yapılır: Tamamlanan görevler arasından seçme](../../parallel/concrt/how-to-select-among-completed-tasks.md).

[[Üst](#top)]

##  <a name="join"></a> birleştirme ve multitype_join sınıfları

[Concurrency::join](../../parallel/concrt/reference/join-class.md) ve [concurrency::multitype_join](../../parallel/concrt/reference/multitype-join-class.md) sınıflar, bir ileti almak bir kaynak kümesi her üyesi için bekleyin olanak tanır. `join` Ortak bir ileti türüne sahip kaynak nesnesi üzerinde sınıf davranır. `multitype_join` İleti farklı türlere sahip olabilen kaynak nesneler üzerinde sınıf davranır.

Okuma bir `join` veya `multitype_join` nesne benzer Windows API işlevi çağırma `WaitForMultipleObjects` sahip olduğunda `bWaitAll` parametresini `TRUE`. Ancak, olduğu gibi bir `choice` nesnesi `join` ve `multitype_join` nesneleri bir dış eşitleme nesnesi için olay yerine veri bağlayan bir olay mekanizması kullanır.

Okuma bir `join` nesne oluşturan bir std::[vektör](../../standard-library/vector-class.md) nesne. Okuma bir `multitype_join` nesne oluşturan bir std::[demet](../../standard-library/tuple-class.md) nesne. Öğeleri görünür aynı sırada bu nesneler, ilgili kaynak arabelleklerini bağlantılı olarak `join` veya `multitype_join` nesne. Kaynak bağlantı siparişi için arabelleğe alır çünkü bir `join` veya `multitype_join` nesnesi elde edilen öğelerin sırasını ile ilişkili olan `vector` veya `tuple` nesnesi, mevcut bir kaynak arabelleğinden bağlantısını değil öneririz bir katılın. Bunun yapılması, belirtilmeyen davranışlara neden olabilir.

### <a name="greedy-versus-non-greedy-joins"></a>Doyumsuz Olmayan Birleştirmelere Karşı Doyumsuz

`join` Ve `multitype_join` sınıfları doyumsuz ve doyumsuz olmayan birleştirmeler kavramını destekler. A *doyumsuz birleştirme* kullanılabilir tüm ileti kadar iletileri kullanılabilir duruma geldiğinde kaynaklarının her bir iletiyi kabul eder. A *doyumsuz olmayan birleştirme* iki aşamada iletileri alır. Doyumsuz olmayan birleştirme ilk olarak, her kaynaklarının bir ileti sunulur bekler. İkinci olarak, tüm kaynak iletileri kullanılabilir olduktan sonra her biri bu iletileri ayırmak doyumsuz olmayan birleştirme çalışır. Her ileti ayırabilirsiniz, tüm iletileri kullanır ve bunları hedefte yayar. Aksi takdirde, serbest bırakır, veya iptal eder, ileti rezervasyonları ve yeniden bir ileti almak her kaynak için bekler.

Doyumsuz birleştirme, doyumsuz olmayan birleştirmeler daha iyi iletileri hemen kabul gerçekleştirilemiyor. Ancak, nadir durumlarda, kilitlenmeler için doyumsuz birleştirme yol açabilir. Doyumsuz olmayan birleştirme, bir veya daha fazla paylaşılan kaynak nesneleri içeren birden fazla birleşim sahip olduğunuzda kullanın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, temel yapısı ile nasıl çalışılacağını gösterir `join` sınıfı. Bu örnekte [concurrency::make_join](reference/concurrency-namespace-functions.md#make_join) oluşturmak için işlevi bir `join` üç alan nesnesi `single_assignment` nesneleri. Bu örnek, çeşitli Fibonacci sayı hesaplar, her sonucu farklı bir depolar `single_assignment` nesnesi ve ardından yazdırır her konsol için neden olan `join` nesne tutar. Bu örnek için örneğe benzer `choice` ancak `join` sınıfı bekleyen tüm kaynak ileti blokları bir ileti alırsınız.

[!code-cpp[concrt-join-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_7.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
fib35 = 9227465fib37 = 24157817half_of_fib42 = 1.33957e+008
```

Bu örnekte [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) paralel Fibonacci sayıları hesaplamak için kullanılan algoritma. Hakkında daha fazla bilgi için `parallel_invoke`, bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

Nasıl kullanılacağını gösteren tam örnekler `join` sınıfı [nasıl yapılır: Tamamlanan görevler arasından seçme](../../parallel/concrt/how-to-select-among-completed-tasks.md) ve [izlenecek yol: Kilitlenmeyi önlemek için birleştirme kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).

[[Üst](#top)]

##  <a name="timer"></a> Zamanlayıcı sınıfı

Eşzamanlılık::[timer sınıfı](../../parallel/concrt/reference/timer-class.md) ileti kaynağı olarak görev yapar. A `timer` nesne belirli bir süre geçtikten sonra bu ileti bir hedefe gönderir. `timer` Sınıfı, bir ileti gönderilirken gecikme gerekir veya düzenli aralıkla ileti gönderme istediğinizde yararlıdır.

`timer` Sınıf için yalnızca bir hedef, ileti gönderir. Ayarlarsanız `_PTarget` oluşturucuda parametre `NULL`, daha sonra hedef çağırarak belirtebileceğiniz [concurrency::ISource::link_target](reference/source-block-class.md#link_target) yöntemi.

A `timer` nesne yinelenen veya yinelenmeyen. Yinelenen bir zamanlayıcı oluşturmak geçirin **true** için `_Repeating` kurucusunu çağırdığınızda parametresi. Aksi halde geçirmek **false** için `_Repeating` yinelenmeyen bir zamanlayıcı oluşturulacağı parametre. Zamanlayıcı yinelenen, her bir süre sonra hedefte aynı iletiyi gönderir.

Agents kitaplığı oluşturur `timer` başlatıldı-durumdaki nesneler. Bir zamanlayıcı nesnesini başlatmak için çağrı [concurrency::timer::start](reference/timer-class.md#start) yöntemi. Durdurmak için bir `timer` nesne, nesne veya çağrı yok [concurrency::timer::stop](reference/timer-class.md#stop) yöntemi. Yinelenen bir zamanlayıcı duraklatmak için çağrı [concurrency::timer::pause](reference/timer-class.md#pause) yöntemi.

### <a name="example"></a>Örnek

Aşağıdaki örnek, temel yapısı ile nasıl çalışılacağını gösterir `timer` sınıfı. Örnekte `timer` ve `call` uzun bir işlemin ilerlemesini bildirmek için nesne.

[!code-cpp[concrt-timer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_8.cpp)]

Bu örnek, örnek aşağıdaki çıktıyı üretir:

```Output
Computing fib(42)..................................................result is 267914296
```

Nasıl kullanılacağını gösteren tam bir örnek `timer` sınıfı [nasıl yapılır: Düzenli aralıkla ileti gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md).

[[Üst](#top)]

##  <a name="filtering"></a> İleti filtreleme

Bir ileti bloğu nesnesi oluştururken sağlayabilirsiniz bir *filtre işlevi* ileti bloğu kabul eder ya da bir ileti reddeder olup olmadığını belirler. Bir filtre işlevi, bir ileti bloğu yalnızca belirli değerleri almasını sağlamak için kullanışlı bir yoldur.

Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `unbounded_buffer` yalnızca çift sayıları kabul etmek için bir filtre işlevi kullanan nesne. `unbounded_buffer` Nesne tek sayıları reddeder ve kendi hedef bloklarından için tek sayıları dağıtılmaz.

[!code-cpp[concrt-filter-function#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_9.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
0 2 4 6 8
```

Bir filtre işlevi lambda işlevi, işlev işaretçisi veya işlev nesnesi olabilir. Her filtre işlevi aşağıdaki biçimlerden birini alır.

```Output
bool (T)
bool (T const &)
```

Gereksiz verilerin kopyalanmasını ortadan kaldırmak için değere göre yayılan bir toplam değer türüne sahip olduğunda ikinci formu kullanın.

İleti filtreleme destekler *veri akışı* hangi bileşenlerin gerçekleştirmek hesaplamalar veri aldıklarında bir programlama modeli. Filtre işlevleri ileti geçirme ağdaki veri akışını denetlemek için kullandığı örnekleri için bkz. [nasıl yapılır: Bir ileti bloğu filtresini kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md), [izlenecek yol: Bir veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md), ve [izlenecek yol: Görüntü işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).

[[Üst](#top)]

##  <a name="reservation"></a> İleti rezervasyonu

*İleti rezervasyonu* daha sonra kullanmak için bir ileti ayırmak üzere bir ileti bloğu sağlar. Genellikle, ileti rezervasyonlarına doğrudan kullanılmaz. Ancak, anlama ileti ayırma daha iyi yardımcı olabilecek bazı önceden tanımlanmış bir ileti bloğu türleri davranışını anlayın.

Doyumsuz olmayan ve doyumsuz birleştirme göz önünde bulundurun. Bunların her ikisi de daha sonra kullanmak için iletileri ayrılacak ileti rezervasyonlarına kullanın. Bir açıklandığı gibi daha önce doyumsuz olmayan birleştirme iletileri iki aşamada alır. Bir doyumsuz olmayan ilk aşamasında `join` nesne her bir ileti almak için kendi kaynakları için bekler. Doyumsuz olmayan birleştirme, her biri bu iletileri ayrılacak sonra çalışır. Her ileti ayırabilirsiniz, tüm iletileri kullanır ve bunları hedefte yayar. Aksi takdirde, serbest bırakır, veya iptal eder, ileti rezervasyonları ve yeniden bir ileti almak her kaynak için bekler.

Ayrıca bir dizi kaynaktan giriş iletileri okur, doyumsuz birleştirme, her bir kaynaktan bir ileti almak için beklerken ek iletileri okumak için ileti rezervasyonlarına kullanır. Örneğin, iletiler alan ileti bloklarından doyumsuz birleştirme düşünün `A` ve `B`. Doyumsuz birleştirme B'den iki ileti alır, ancak henüz bir ileti alındı `A`, doyumsuz birleştirme ikinci iletisinden benzersiz İleti tanımlayıcısı kaydeder `B`. Doyumsuz birleştirme gelen iletiyi aldıktan sonra `A` ve bu iletileri, ikinci gelen ileti olmadığını görmek için kaydedilen iletinin tanımlayıcısı kullandığı `B` hala kullanılabilir.

Kendi özel ileti bloğu türleri uyguladığınızda, ileti rezervasyonlarına kullanabilirsiniz. Özel ileti bloğu türünün nasıl oluşturulacağı hakkında bir örnek için bkz [izlenecek yol: Özel ileti bloğu oluşturma](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md).

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)
