---
title: "Zaman uyumsuz ileti blokları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- non-greedy join [Concurrency Runtime]
- asynchronous message blocks
- greedy join [Concurrency Runtime]
ms.assetid: 79c456c0-1692-480c-bb67-98f2434c1252
caps.latest.revision: "36"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1e2c2641ada0f6bbcd1b19c4297ba85b3bb4d393
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="asynchronous-message-blocks"></a>Zaman Uyumsuz İleti Blokları

Aracılar Kitaplığı iletileri uygulama bileşenleri arasında bir iş parçacığı açısından güvenli şekilde yayılmasına olanak tanıyan çeşitli ileti bloğu türler sağlar. Bu ileti bloğu türleri genellikle çeşitli ileti geçirme yordamları ile aşağıdaki gibi kullanılır [concurrency::send](reference/concurrency-namespace-functions.md#send), [concurrency::asend](reference/concurrency-namespace-functions.md#asend), [concurrency::receive](reference/concurrency-namespace-functions.md#receive), ve [concurrency::try_receive](reference/concurrency-namespace-functions.md#try_receive). İleti Aracılar Kitaplığı tarafından tanımlanan yordamları geçirme hakkında daha fazla bilgi için bkz: [ileti geçirme işlevleri](../../parallel/concrt/message-passing-functions.md).  
  
##  <a name="top"></a>Bölümler  
 Bu konu aşağıdaki bölümleri içermektedir:  
  
- [Kaynakları ve hedefleri](#sources_and_targets)  
  
- [İleti yayma](#propagation)  
  
- [İleti bloğu türlerine genel bakış](#overview)  
  
- [unbounded_buffer sınıfı](#unbounded_buffer)  
  
- [overwrite_buffer sınıfı](#overwrite_buffer)  
  
- [single_assignment sınıfı](#single_assignment)  
  
- [Çağrı sınıfı](#call)  
  
- [Transformer sınıfı](#transformer)  
  
- [seçenek sınıfı](#choice)  
  
- [katılma ve multitype_join sınıfları](#join)  
  
- [Timer sınıfı](#timer)  
  
- [İleti filtreleme](#filtering)  
  
- [İleti ayırma](#reservation)  
  
##  <a name="sources_and_targets"></a>Kaynakları ve hedefleri  
 Kaynakları ve hedefleri ileti geçirme iki önemli katılımcıları var. A *kaynak* iletileri gönderir iletişim için bir uç nokta başvuruyor. A *hedef* iletileri alan iletişim için bir uç nokta başvuruyor. Okuma, bir uç nokta olarak bir kaynak ve hedef için yazma bir uç nokta olarak düşünebilirsiniz. Uygulamalar, form için kaynakları ve hedefleri birlikte bağlanmak *ağlar Mesajlaşma*.  
  
 Aracılar Kitaplığı kaynakları ve hedefleri temsil etmek için iki soyut sınıflar kullanır: [concurrency::ISource](../../parallel/concrt/reference/isource-class.md) ve [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md). İleti bloğu türleri bu act kaynakları türetin gibi `ISource`; ileti bloğu türleri bu act hedefleri türetin gibi `ITarget`. İleti bloğu kaynakları olarak bu eylemi türleri ve hedefleri türetilen hem de `ISource` ve `ITarget`.  
  
 [[Üst](#top)]  
  
##  <a name="propagation"></a>İleti yayma  
 *İleti yayma* bir bileşenden ileti gönderme, işlemidir. İleti bloğu bir ileti sunulduğunda bunu kabul, reddetme veya ileti erteleyin. Her ileti blok türü depolar ve iletileri farklı şekilde iletir. Örneğin, `unbounded_buffer` sınıfı depolar iletileri, sınırsız sayıda `overwrite_buffer` sınıfı, bir kerede tek bir ileti depolar ve her iletinin değiştirilmiş bir sürümünü transformer sınıfını depolar. Bu ileti bloğu türleri, bu belgenin ilerleyen bölümlerinde daha ayrıntılı açıklanmıştır.  
  
 İleti bloğu bir ileti kabul ettiğinde, bunu isteğe bağlı olarak çalışmayı gerçekleştirmek ve, ileti bloğu, kaynak ise elde edilen iletisi ağ başka bir üyesi geçirin. İleti bloğu almaya istemediği iletileri reddetmek için bir filtre işlevini kullanabilirsiniz. Filtreler bölümündeki bu konunun ilerleyen bölümlerinde daha ayrıntılı açıklanmıştır [ileti filtreleme](#filtering). Bir ileti erteler bir ileti bloğu ileti ayırabilir ve daha sonra kullanabilir. İleti ayırma bölümünde bu konunun ilerleyen bölümlerinde daha ayrıntılı anlatılan [ileti ayırma](#reservation).  
  
 Aracılar Kitaplığı zaman uyumsuz ileti blokları etkinleştirir veya zaman uyumlu olarak iletileri geçirin. Geçirdiğiniz zaman bir ileti için ileti bloğu eşzamanlı olarak, örneğin, kullanarak `send` işlevi, çalışma zamanı engeller geçerli bağlamı kadar hedef blok kabul eder ya da ileti reddeder. Geçirdiğiniz zaman bir ileti için ileti bloğu zaman uyumsuz olarak, örneğin, kullanarak `asend` işlevi, hedef iletiye çalışma zamanı sunar ve ileti hedef kabul ederse, çalışma zamanı ileti yayar zaman uyumsuz bir görevi zamanlar. alıcıya. Çalışma zamanı Basit görevler iletilerini İşbirlikçi bir şekilde dağıtmak için kullanır. Basit görevler hakkında daha fazla bilgi için bkz: [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  

 Uygulamaları kaynakları ve hedefleri birlikte ağları ileti biçimine bağlayın. Genellikle, arama ve ağ bağlantı `send` veya `asend` ağa veri iletmek için. Bir hedef kaynak ileti bloğu bağlanmak için çağrı [concurrency::ISource::link_target](reference/isource-class.md#link_target) yöntemi. Bir hedef kaynak blok bağlantısını kesmek için çağrı [concurrency::ISource::unlink_target](reference/isource-class.md#unlink_target) yöntemi. Bir kaynak bloğu tüm hedeflerine bağlantısını kesmek için çağrı [concurrency::ISource::unlink_targets](reference/isource-class.md#unlink_targets) yöntemi. Önceden tanımlanmış ileti bloğu türlerinden birini kapsam dışına çıktığında veya kaldırıldığı zaman, otomatik olarak kendisini herhangi hedef bloklarından bağlantısını keser. Bazı ileti bloğu türleri için yazabilirsiniz hedefleri sayısını sınırlayın. Aşağıdaki bölümde, önceden tanımlanmış ileti bloğu türleri için geçerli kısıtlamaları açıklar.  
  
 [[Üst](#top)]  
  
##  <a name="overview"></a>İleti bloğu türlerine genel bakış  
 Aşağıdaki tabloda, önemli ileti bloğu türlerinin rolü kısaca açıklanmaktadır.  
  
 [unbounded_buffer](#unbounded_buffer)  
 İletileri kuyruğunu depolar.  
  
 [overwrite_buffer](#overwrite_buffer)  
 Yazılan ve birden çok kez okuma tek bir ileti depolar.  
  
 [single_assignment](#single_assignment)  
 Aynı anda yazılmış ve birden çok kez okuma tek bir ileti depolar.  
  
 [Arama](#call)  
 Bir ileti aldığında çalışma gerçekleştirir.  
  
 [Transformer](#transformer)  
 İş verileri alır ve bu iş sonucunu başka bir hedef blok gönderir gerçekleştirdiğinde. `transformer` Farklı bir giriş ve çıkış türlerde sınıfı işlevi görebilir.  
  
 [Seçim](#choice)  
 İlk kullanılabilir ileti kaynaklarını kümesinden seçer.  
  
 [katılma ve multitype birleştirme](#join)  
 Kaynakları kümesinden alınması ve başka bir ileti bloğu için bir ileti iletileri birleştirebilirsiniz tüm iletiler için bekleyin.  
  
 [Zamanlayıcı](#timer)  
 İleti için hedef blok düzenli aralıklarla gönderir.  
  
 Bu ileti bloğu türleri farklı durumlarda kullanışlı hale getirmek farklı özelliklere sahip. Bu özelliklerin bazıları şunlardır:  
  
- *Yayma türü*: olup ileti bloğu veri, alıcı veri ya da her ikisini de kaynağı olarak davranır.  
  
- *İleti Sıralama*: ileti bloğu iletileri, gönderilen veya alınan özgün sipariş olup korur. Her önceden tanımlanmış ileti blok türü, gönderdiğinde veya iletileri alan özgün sipariş tutar.  
  
- *Kaynak sayısı*: ileti bloğu okuyabileceği kaynakları maksimum sayısı.  
  
- *Hedef sayısı*: ileti bloğu yazabilirler hedef maksimum sayısı.  
  
 Aşağıdaki tabloda, bu özelliklere ileti bloğu çeşitli nasıl ilişkili olduğunu gösterir.  
  
|İleti blok türü|Yayma türü (kaynak, hedef veya her ikisi de)|İleti (sipariş edilmiş veya Unordered) sıralama|Kaynak sayısı|Hedef sayısı|  
|------------------------|--------------------------------------------------|-----------------------------------------------|------------------|------------------|  
|`unbounded_buffer`|Her ikisi|sıralı|sınırsız|sınırsız|  
|`overwrite_buffer`|Her ikisi|sıralı|sınırsız|sınırsız|  
|`single_assignment`|Her ikisi|sıralı|sınırsız|sınırsız|  
|`call`|Hedef|sıralı|sınırsız|Uygulanamaz|  
|`transformer`|Her ikisi|sıralı|sınırsız|1.|  
|`choice`|Her ikisi|sıralı|10|1.|  
|`join`|Her ikisi|sıralı|sınırsız|1.|  
|`multitype_join`|Her ikisi|sıralı|10|1.|  
|`timer`|Kaynak|Uygulanamaz|Uygulanamaz|1.|  
  
 Aşağıdaki bölümlerde daha ayrıntılı ileti bloğu türleri açıklanmaktadır.  
  
 [[Üst](#top)]  
  
##  <a name="unbounded_buffer"></a>unbounded_buffer sınıfı  
 [Concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) sınıfı, genel amaçlı bir zaman uyumsuz Mesajlaşma yapısını temsil eder. Bu sınıf, iletilerin birden çok kaynak tarafından yazılabilen veya birden çok hedef tarafından okunabilen bir ilk giren ilk çıkar (FIFO) sırasını tutar. Ne zaman bir hedef alan bir iletiden bir `unbounded_buffer` nesnesi, bu iletiyi, ileti kuyruğundan kaldırılır. Bu nedenle, ancak bir `unbounded_buffer` nesne birden çok hedef sahip olabilir, yalnızca bir hedef, her bir ileti alırsınız. `unbounded_buffer` sınıfı, başka bir bileşene birden çok ileti geçirmek istediğinizde ve bu bileşenin her iletiyi alması gerektiğinde kullanışlıdır.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek ile nasıl çalışılacağını temel yapısını gösterir `unbounded_buffer` sınıfı. Bu örnekte, üç değerden gönderilir bir `unbounded_buffer` nesne ve daha sonra bu değerler aynı nesneden okur.  
  
 [!code-cpp[concrt-unbounded_buffer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_1.cpp)]  
  
 Bu örnek şu çıkışı üretir:  
  
```Output  
334455  
```  
  
 Nasıl kullanılacağını gösteren tam bir örnek için `unbounded_buffer` sınıfı için bkz: [nasıl yapılır: çeşitli üretici-tüketici desenlerini uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md).  
  
 [[Üst](#top)]  
  
##  <a name="overwrite_buffer"></a>overwrite_buffer sınıfı  
 [Concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) sınıfı benzer `unbounded_buffer` ; tek fark sınıfı bir `overwrite_buffer` nesnesi yalnızca bir ileti saklar. Buna ek olarak, ne zaman bir hedef alan bir iletiden bir `overwrite_buffer` nesnesi, bu iletiyi arabelleğinden kaldırılmaz. Bu nedenle, birden çok hedef iletinin bir kopyasını alır.  
  
 `overwrite_buffer` Sınıfı, birden fazla ileti başka bir bileşenine geçmek istiyor ancak yalnızca en son değer belirli bir bileşeni gerektiren durumlarda yararlıdır. Bu sınıf, bir iletiyi birden çok bileşene yayınlamak istediğinizde de kullanışlıdır.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek ile nasıl çalışılacağını temel yapısını gösterir `overwrite_buffer` sınıfı. Bu örnekte, üç değerden gönderilir bir `overwrite _buffer` nesne ve daha sonra geçerli değeri aynı nesneden üç kez okur. Bu örnek için örnek benzer `unbounded_buffer` sınıfı. Ancak, `overwrite_buffer` sınıfı yalnızca bir ileti depolar. Ayrıca, çalışma zamanı iletiden kaldırmaz bir `overwrite_buffer` onu okuduktan sonra nesnesi.  
  
 [!code-cpp[concrt-overwrite_buffer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_2.cpp)]  
  
 Bu örnek şu çıkışı üretir:  
  
```Output  
555555  
```  
  
 Nasıl kullanılacağını gösteren tam bir örnek için `overwrite_buffer` sınıfı için bkz: [nasıl yapılır: çeşitli üretici-tüketici desenlerini uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md).  
  
 [[Üst](#top)]  
  
##  <a name="single_assignment"></a>single_assignment sınıfı  
 [Concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) sınıfı benzer `overwrite_buffer` ; tek fark sınıfı bir `single_assignment` nesne yalnızca bir kez yazılabilir. `overwrite_buffer` sınıfı gibi, hedef de bir `single_assignment` nesnesinden ileti aldığında, o ileti nesneden kaldırılmaz. Bu nedenle, birden çok hedef iletinin bir kopyasını alır. `single_assignment` Sınıfı, birden çok bileşeni tek bir ileti yayın istediğinizde yararlıdır.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek ile nasıl çalışılacağını temel yapısını gösterir `single_assignment` sınıfı. Bu örnekte, üç değerden gönderilir bir `single_assignment` nesne ve daha sonra geçerli değeri aynı nesneden üç kez okur. Bu örnek için örnek benzer `overwrite_buffer` sınıfı. Olsa da hem `overwrite_buffer` ve `single_assignment` sınıfları depolamak tek bir ileti `single_assignment` sınıfı yalnızca bir kez yazılabilir.  
  
 [!code-cpp[concrt-single_assignment-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_3.cpp)]  
  
 Bu örnek şu çıkışı üretir:  
  
```Output  
333333  
```  
  
 Nasıl kullanılacağını gösteren tam bir örnek için `single_assignment` sınıfı için bkz: [izlenecek yol: vadeli uygulama](../../parallel/concrt/walkthrough-implementing-futures.md).  
  
 [[Üst](#top)]  
  
##  <a name="call"></a>Çağrı sınıfı  
 [Concurrency::call](../../parallel/concrt/reference/call-class.md) veri aldığında, bir iş işlevi gerçekleştiren bir ileti alıcısı sınıf görevi görür. Bu çalışma işlevi bir lambda ifadesi, bir işlev nesnesi veya bir işlev işaretçisi olabilir. A `call` nesne davranır sıradan işlev çağrısı'den farklı bileşenlerle iletileri göndermek için paralel davrandığından. Varsa bir `call` nesnesi bir ileti aldığında çalışma gerçekleştirme, bu iletiyi kuyruğa ekler. Her `call` nesne işlemleri sıraya alınan iletileri bunlar alınan sırayla.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek ile nasıl çalışılacağını temel yapısını gösterir `call` sınıfı. Bu örnekte bir `call` konsola alan her değerin yazdırır nesnesi. Örnek, ardından üç değerden gönderir `call` nesnesi. Çünkü `call` nesnesini işler iletileri ayrı bir iş parçacığı üzerinde bu örnek ayrıca bir sayaç değişkenini kullanır ve bir [olay](../../parallel/concrt/reference/event-class.md) emin olmak için nesne `call` nesnesini işler önce tüm iletileri `wmain` işlevi döndürür.  
  
 [!code-cpp[concrt-call-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_4.cpp)]  
  
 Bu örnek şu çıkışı üretir:  
  
```Output  
334455  
```  
  
 Nasıl kullanılacağını gösteren tam bir örnek için `call` sınıfı için bkz: [nasıl yapılır: call ve transformer sınıflarına iş işlevleri sağlayan](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md).  
  
 [[Üst](#top)]  
  
##  <a name="transformer"></a>Transformer sınıfı  
 [Concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) sınıfı bir ileti gönderen ve her iki ileti alıcı olarak davranır. `transformer` Sınıfı benzer `call` veri aldığında, kullanıcı tanımlı bir iş işlev gerçekleştirdiğinden sınıfı. Ancak, `transformer` sınıfı ayrıca iş işlevin sonucu alıcı nesnelere gönderir. Gibi bir `call` nesne, bir `transformer` nesne davranır paralel iletileri gönder diğer bileşenleri. Varsa bir `transformer` nesnesi bir ileti aldığında çalışma gerçekleştirme, bu iletiyi kuyruğa ekler. Her `transformer` nesnesini, sıraya alınan iletileri bunlar alınan sırayla işler.  
  
 `transformer` Sınıfı için bir hedef kendi iletisi gönderir. Ayarlarsanız `_PTarget` oluşturucuya parametresinde `NULL`, daha sonra hedef çağırarak belirleyebileceğiniz [concurrency::link_target](reference/source-block-class.md#link_target) yöntemi.  
  
 Aracılar Kitaplığı tarafından sağlanan tüm diğer zaman uyumsuz ileti bloğu türleri aksine `transformer` farklı bir giriş ve çıkış türlerde sınıfı işlevi görebilir. Bu özelliği başka bir hale gelmesi için verileri bir türden diğerine dönüştürün `transformer` kilit bir bileşeni çok sayıda eş zamanlı ağlardaki sınıfı. Ayrıca, daha fazla hassas paralel işlevsellik, iş işlevinde ekleyebilirsiniz bir `transformer` nesnesi.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek ile nasıl çalışılacağını temel yapısını gösterir `transformer` sınıfı. Bu örnekte bir `transformer` katları her giriş nesnesi `int` değeri üretmek için 0.33 tarafından bir `double` değer olarak çıktı. Örnek sonra dönüştürülmüş değerleri aynı alır `transformer` nesne ve bunları konsola yazdırır.  
  
 [!code-cpp[concrt-transformer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_5.cpp)]  
  
 Bu örnek şu çıkışı üretir:  
  
```Output  
10.8914.5218.15  
```  
  
 Nasıl kullanılacağını gösteren tam bir örnek için `transformer` sınıfı için bkz: [nasıl yapılır: veri ardışık düzeninde transformer kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).  
  
 [[Üst](#top)]  
  
##  <a name="choice"></a>seçenek sınıfı  
 [Concurrency::choice](../../parallel/concrt/reference/choice-class.md) sınıfı kaynakları kümesinden ilk kullanılabilir ileti seçer. `choice` Sınıfı, bir veri akışı mekanizması yerine akış denetimi mekanizmasını temsil eder (konu [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) veri akışı ve akış denetimi arasındaki farklar açıklanmaktadır).  
  
 Bir seçim nesnesinden okuma benzer Windows API işlevi çağırma `WaitForMultipleObjects` sahip olduğunda `bWaitAll` parametre kümesine `FALSE`. Ancak, `choice` sınıfı, bir dış eşitleme nesnesi için olay kendisi yerine veri bağlar.  
  

 Genellikle, kullandığınız `choice` ile birlikte sınıf [concurrency::receive](reference/concurrency-namespace-functions.md#receive) akış denetimi uygulamanızda sürücü işlevi. Kullanım `choice` farklı türlerine sahip ileti arabelleklerinin arasında seçmeniz gerektiğinde sınıfı. Kullanım `single_assignment` aynı türe sahip ileti arabelleklerinin arasında seçmeniz gerektiğinde sınıfı.  

  
 Kaynaklar için bağlantı sipariş bir `choice` nesnesi, ileti seçili belirleyebildiğinden önemlidir. Örneğin, bağlantı burada zaten bir iletiye içeren birden çok ileti arabelleklerinin durumu göz önünde bulundurun bir `choice` nesnesi. `choice` Nesnesi bağlı olduğu ilk kaynağından ileti seçer. Tüm kaynakları bağladıktan sonra `choice` nesne her kaynak bir ileti alır sipariş korur.  
  
### <a name="example"></a>Örnek  

 Aşağıdaki örnek ile nasıl çalışılacağını temel yapısını gösterir `choice` sınıfı. Bu örnekte [concurrency::make_choice](reference/concurrency-namespace-functions.md#make_choice) işlevi oluşturmak için bir `choice` arasında üç ileti blokları seçer nesnesi. Örnek ardından çeşitli Fibonacci numaraları hesaplar ve her sonucu farklı ileti bloğu'depolar. Örnek daha sonra ilk tamamlandı işlemi temel alan bir ileti konsola yazdırır.  

  
 [!code-cpp[concrt-choice-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_6.cpp)]  
  
 Bu örnekte aşağıdaki örnek çıkışı üretir:  
  
```Output  
fib35 received its value first. Result = 9227465  
```  
  
 Çünkü 35 hesaplar görev<sup>th</sup> Fibonacci numarası garanti edilmez ilk olarak, bu örnek çıktı değişebilir.  
  

 Bu örnekte [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) Fibonacci sayıları paralel işlem algoritması. Hakkında daha fazla bilgi için `parallel_invoke`, bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).  
  
 Nasıl kullanılacağını gösteren tam bir örnek için `choice` sınıfı için bkz: [nasıl yapılır: Tamamlanan görevler arasından seçin](../../parallel/concrt/how-to-select-among-completed-tasks.md).  
  
 [[Üst](#top)]  
  
##  <a name="join"></a>katılma ve multitype_join sınıfları  
 [Concurrency::join](../../parallel/concrt/reference/join-class.md) ve [concurrency::multitype_join](../../parallel/concrt/reference/multitype-join-class.md) bir ileti almak bir kaynak kümesi her üyesi için bekleyin sınıfları sağlar. `join` Ortak bir ileti türüne sahip kaynak nesneler üzerinde sınıf davranır. `multitype_join` Sınıfı davranır Kaynak nesnelerde farklı ileti türü olabilir.  
  
 Okuma bir `join` veya `multitype_join` nesne benzer Windows API işlevi çağırma `WaitForMultipleObjects` sahip olduğunda `bWaitAll` parametre kümesine `TRUE`. Ancak, olduğu gibi bir `choice` nesnesi `join` ve `multitype_join` nesneleri olayın kendisi yerine bir dış eşitleme nesnesi için veri bağlar bir olay mekanizması kullanır.  
  
 Okuma bir `join` nesne üreten bir std::[vektör](../../standard-library/vector-class.md) nesnesi. Okuma bir `multitype_join` nesne üreten bir std::[tanımlama grubu](../../standard-library/tuple-class.md) nesnesi. Öğeleri görünür bu nesneler aynı sırayla karşılık gelen kaynak arabelleklerini bağlantılı olarak `join` veya `multitype_join` nesnesi. Kaynak bağlantı sipariş arabelleğe alır çünkü bir `join` veya `multitype_join` nesnesidir elde edilen içinde öğelerin sırasını ilişkilendirilmiş `vector` veya `tuple` nesnesi, var olan bir kaynak arabelleğinden bağlantısını değil öneririz bir birleştirme. Bunun yapılması, belirtilmeyen davranışlara neden olabilir.  
  
### <a name="greedy-versus-non-greedy-joins"></a>Doyumsuz Olmayan Birleştirmelere Karşı Doyumsuz  
 `join` Ve `multitype_join` sınıfları doyumsuz ve doyumsuz olmayan birleştirmeler kavramı destekler. A *doyumsuz birleştirme* tüm ileti kadar kullanılabilir iletileri kullanılabilir duruma geldiğinde her biri kendi kaynaklarını iletiden kabul eder. A *doyumsuz olmayan birleştirme* iki aşamada iletilerini alır. Doyumsuz olmayan birleştirme ilk olarak, her kaynaklarının bir ileti sunulur bekler. İkinci olarak, tüm kaynak iletileri kullanılabilir olduktan sonra her bu iletilerin ayrılacak doyumsuz olmayan birleştirme çalışır. Her ileti ayırabilirsiniz, tüm iletileri kullanır ve hedefte yayar. Aksi takdirde, serbest bırakır, ya da iptal eder, ileti ayırmaları ve yeniden bir ileti almak her kaynak için bekler.  
  
 Doyumsuz birleştirme doyumsuz olmayan birleştirmeler daha iyi iletileri hemen kabul gerçekleştirilemiyor. Ancak, ender durumlarda doyumsuz birleştirme kilitlenmeye neden olabilir. Doyumsuz olmayan birleştirme, bir veya daha fazla paylaşılan kaynak nesneleri içeren birden fazla birleşim sahip olduğunuzda kullanın.  
  
### <a name="example"></a>Örnek  

 Aşağıdaki örnek ile nasıl çalışılacağını temel yapısını gösterir `join` sınıfı. Bu örnekte [concurrency::make_join](reference/concurrency-namespace-functions.md#make_join) işlevi oluşturmak için bir `join` üç alan nesnesi `single_assignment` nesneleri. Bu örnek çeşitli Fibonacci numaraları hesaplar, her bir sonucu farklı bir depolar `single_assignment` nesnesi ve her konsoluna sonra baskı siparişi neden, `join` nesne ayrı tutma. Bu örnek için örnek benzer `choice` ; tek fark sınıfı `join` sınıfı bekler tüm kaynak ileti blokları bir ileti alırsınız.  
  
 [!code-cpp[concrt-join-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_7.cpp)]  
  
 Bu örnek şu çıkışı üretir:  
  
```Output  
fib35 = 9227465fib37 = 24157817half_of_fib42 = 1.33957e+008  
```  

 Bu örnekte [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) Fibonacci sayıları paralel işlem algoritması. Hakkında daha fazla bilgi için `parallel_invoke`, bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).  
  
 Nasıl kullanılacağını gösteren tam örnekleri için `join` sınıfı için bkz: [nasıl yapılır: Tamamlanan görevler arasından seçin](../../parallel/concrt/how-to-select-among-completed-tasks.md) ve [izlenecek yol: kilitlenmeyi önlemek için birleştirme birleşim kullanılarak](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).  
  
 [[Üst](#top)]  
  
##  <a name="timer"></a>Timer sınıfı  
 Eşzamanlılık::[timer sınıfı](../../parallel/concrt/reference/timer-class.md) bir ileti kaynağı olarak görev yapar. A `timer` nesne belirtilen bir süre dolduktan sonra bu ileti bir hedefe gönderir. `timer` Sınıfı, bir ileti gönderirken gecikme gerekir veya düzenli aralıklarla ileti gönderme istediğinizde yararlıdır.  
  

 `timer` Sınıfı için yalnızca bir hedef kendi iletisi gönderir. Ayarlarsanız `_PTarget` oluşturucuya parametresinde `NULL`, daha sonra hedef çağırarak belirleyebileceğiniz [concurrency::ISource::link_target](reference/source-block-class.md#link_target) yöntemi.  

  
 A `timer` nesne yinelenen veya yinelenmeyen. Yinelenen bir zamanlayıcı oluşturmak için geçirmek `true` için `_Repeating` Oluşturucusu çağırdığınızda parametresi. Aksi takdirde geçirmek `false` için `_Repeating` yinelenmeyen süreölçer oluşturmak için parametre. Zamanlayıcı yinelenen varsa, her zaman aralığından sonra hedefte aynı iletiyi gönderir.  
  
 Aracılar Kitaplığı oluşturur `timer` başlatıldı-durumdaki nesneler. Bir zamanlayıcı nesnesi başlatmak için arama [concurrency::timer::start](reference/timer-class.md#start) yöntemi. Durdurmak için bir `timer` nesne, nesne veya çağrı destroy [concurrency::timer::stop](reference/timer-class.md#stop) yöntemi. Yinelenen bir zamanlayıcı duraklatmak için çağrı [concurrency::timer::pause](reference/timer-class.md#pause) yöntemi.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek ile nasıl çalışılacağını temel yapısını gösterir `timer` sınıfı. Örnek kullanır `timer` ve `call` uzun bir işlemin ilerlemesini bildirmek için nesneleri.  
  
 [!code-cpp[concrt-timer-structure#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_8.cpp)]  
  
 Bu örnekte aşağıdaki örnek çıkışı üretir:  
  
```Output  
Computing fib(42)..................................................result is 267914296  
```  
  
 Nasıl kullanılacağını gösteren tam bir örnek için `timer` sınıfı için bkz: [nasıl yapılır: düzenli aralıkla ileti gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md).  
  
 [[Üst](#top)]  
  
##  <a name="filtering"></a>İleti filtreleme  
 İleti bloğu nesne oluşturduğunuzda, sağlayabilir bir *filtre işlevi* ileti bloğu kabul ediyor veya bir ileti reddeder olup olmadığını belirler. Filter işlevi bir ileti bloğu yalnızca belirli değerlerin aldığını güvence altına almak için kullanışlı bir yoludur.  
  
 Aşağıdaki örnekte nasıl oluşturulacağını gösterir bir `unbounded_buffer` yalnızca çift sayıları kabul etmek için bir filtre işlevi kullandığı nesne. `unbounded_buffer` Nesnesi tek sayıları reddeder ve bu nedenle, hedef bloklarına tek sayıları dağıtılmaz.  
  
 [!code-cpp[concrt-filter-function#1](../../parallel/concrt/codesnippet/cpp/asynchronous-message-blocks_9.cpp)]  
  
 Bu örnek şu çıkışı üretir:  
  
```Output  
0 2 4 6 8  
```  
  
 Filter işlevi lambda işlevi, bir işlev işaretçisi veya işlev nesnesi olabilir. Her filtre işlevi aşağıdaki biçimlerden birini alır.  
  
```Output  
bool (T)  
bool (T const &)  
```  
  
 Gereksiz verilerin kopyalanmasını ortadan kaldırmak için değeri tarafından yayılan bir toplama türü olduğunda ikinci formu kullanın.  
  
 İleti destekler filtreleme *veri akışı* hangi bileşenlerin gerçekleştirmek hesaplamalar veri aldıklarında programlama modeli. Bir ileti geçirme ağdaki veri akışını denetlemek için filtre işlevlerini kullanan örnekler için bkz [nasıl yapılır: ileti bloğu filtresini kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md), [izlenecek yol: bir veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md), ve [ İzlenecek yol: bir görüntü işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).  
  
 [[Üst](#top)]  
  
##  <a name="reservation"></a>İleti ayırma  
 *İleti ayırma* daha sonra kullanmak için bir ileti ayırmak bir ileti bloğu sağlar. Genellikle, ileti ayırma doğrudan kullanılmaz. Ancak, anlama ileti ayırma daha iyi yardımcı olabilecek bazı önceden tanımlanmış ileti bloğu türleri davranışını anlayın.  
  
 Doyumsuz olmayan ve doyumsuz birleştirme göz önünde bulundurun. Bunların her ikisi de iletileri sonraki kullanımlar için ayrılacak ileti ayırma kullanın. Bir açıklanan daha önce doyumsuz olmayan birleştirme iletilerini iki aşamada alır. Bir doyumsuz olmayan ilk aşamasında `join` nesne her bir ileti almak için kaynakları için bekler. Doyumsuz olmayan birleştirme sonra her bu iletiler bir yedek dener. Her ileti ayırabilirsiniz, tüm iletileri kullanır ve hedefte yayar. Aksi takdirde, serbest bırakır, ya da iptal eder, ileti ayırmaları ve yeniden bir ileti almak her kaynak için bekler.  
  
 Ayrıca bir dizi kaynaktan giriş iletileri okur, bir doyumsuz birleştirme, her kaynaktan bir ileti almak için beklerken ek iletiler okumak için ileti ayırma kullanır. Örneğin, ileti blokları iletileri alan bir doyumsuz birleştirme göz önünde bulundurun `A` ve `B`. Doyumsuz birleştirme B'den iki iletilerini alır, ancak henüz bir iletiden almadı `A`, ikinci iletiden benzersiz İleti tanımlayıcısı doyumsuz birleştirme kaydeder `B`. Doyumsuz birleştirme gelen iletiyi aldıktan sonra `A` ve yayar bu iletileri, ikinci gelen ileti olmadığını görmek için kaydedilen iletinin tanımlayıcısı kullandığı `B` hala kullanılabilir.  
  
 Kendi özel ileti bloğu türleri uyguladığınızda ileti ayırması kullanabilirsiniz. Özel ileti blok türü oluşturma konusunda bir örnek için bkz: [izlenecek yol: özel bir ileti bloğu oluşturma](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md).  
  
 [[Üst](#top)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman uyumsuz aracılar kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)

