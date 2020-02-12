---
title: 'İzlenecek yol: Kilitlenmeyi Önlemek için birleştirme kullanma'
ms.date: 04/25/2019
helpviewer_keywords:
- preventing deadlock with joins [Concurrency Runtime]
- deadlock, preventing [Concurrency Runtime]
- non-greedy joins, example
- join class, example
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
ms.openlocfilehash: 4df83e944552fd6c0d2482efa72883d87cd45f8c
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140649"
---
# <a name="walkthrough-using-join-to-prevent-deadlock"></a>İzlenecek yol: Kilitlenmeyi Önlemek için birleştirme kullanma

Bu konuda, uygulamanızda kilitlenmeyi engellemek için [concurrency:: JOIN](../../parallel/concrt/reference/join-class.md) sınıfının nasıl kullanılacağını göstermek üzere ınmpalama filozoflar sorunu kullanılmaktadır. Bir yazılım uygulamasında, iki veya daha fazla işlem bir kaynağı her tutar ve başka bir işlemin başka bir kaynağı serbest bırakma işlemini karşılıklı olarak beklemek durumunda *kilitlenme* oluşur.

Yemek filozoflar sorunu, bir kaynak kümesi birden çok eş zamanlı işlem arasında paylaşıldığında oluşabilecek genel sorun kümesine özgü bir örnektir.

## <a name="prerequisites"></a>Prerequisites

Bu yönergeyi başlamadan önce aşağıdaki konuları okuyun:

- [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)

- [İzlenecek Yol: Aracı Temelli Uygulama Oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)

- [Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)

## <a name="top"></a>Başlıklı

Bu izlenecek yol aşağıdaki bölümleri içerir:

- [Dining filozoflar sorunu](#problem)

- [Bir Naïve uygulama](#deadlock)

- [Kilitlenmeyi engellemek için birleştirmeyi kullanma](#solution)

## <a name="problem"></a>Dining filozoflar sorunu

Yemek filozoflar sorunu, bir uygulamada kilitlenmenin nasıl oluştuğunu gösterir. Bu sorun, yuvarlak bir tabloda beş filozoflar sıya. Her philosopher, düşünce ve Eating arasında alternatifler. Her philosopher, komşuyla komşu ile bir Chopstick paylaşmalıdır ve sağ komşu ile başka bir Chopstick. Aşağıdaki çizimde bu düzen gösterilmektedir.

![Dining filozoflar sorunu](../../parallel/concrt/media/dining_philosophersproblem.png "Yemek Yiyen Filozoflar Sorunu")

Çıkarmak için bir philosopher iki chopsticks olmalıdır. Her philosopher yalnızca bir Chopstick barındırır ve başka bir tane bekliyorsa, hiçbir philosopher ve tüm starve.

[[Üst](#top)]

## <a name="deadlock"></a>Bir Naïve uygulama

Aşağıdaki örnek, Naïve filozoflar sorununun bir uygulamasını gösterir. [Concurrency:: Agent](../../parallel/concrt/reference/agent-class.md)' den türetilen `philosopher` sınıfı, her philosopher bağımsız olarak hareket etmesini sağlar. Örnek, her bir `philosopher` nesnesine bir Chopsticks çiftine özel erişim sağlamak için bir [eşzamanlılık:: critical_section](../../parallel/concrt/reference/critical-section-class.md) nesneleri paylaşılan dizisini kullanır.

Uygulamanın çizim ile ilişkilendirilmesi için `philosopher` sınıfı bir philosopher temsil eder. `int` değişken her bir Chopstick temsil eder. `critical_section` nesneler, Chopsticks Rest 'in bulunduğu sahiplerini sunar. `run` yöntemi philosopher ömrünü taklit eder. `think` yöntemi, düşünce Yasası taklit eder ve `eat` yöntemi, ekip uygulamasının benzetimini yapar.

`philosopher` nesne, `eat` yöntemini çağırmadan önce Chopsticks 'in sahiplerini kaldırma benzetimi yapmak için hem `critical_section` nesnelerini kilitler. `eat`çağrısından sonra, `philosopher` nesnesi `critical_section` nesnelerini kilitlenmemiş duruma geri ayarlayarak Chopsticks ' ı döndürür.

`pickup_chopsticks` yöntemi, kilitlenmenin nerede gerçekleşebileceğini gösterir. Her `philosopher` nesne kilitlenmesiz birine erişirse, diğer kilit başka bir `philosopher` nesnesi tarafından denetlendiği için hiçbir `philosopher` nesne devam edebilir.

### <a name="example"></a>Örnek

[!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_1.cpp)]

### <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `philosophers-deadlock.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc Philosophers-Deadlock. cpp**

[[Üst](#top)]

## <a name="solution"></a>Kilitlenmeyi engellemek için birleştirmeyi kullanma

Bu bölümde, kilitlenme olasılığını ortadan kaldırmak için ileti arabelleklerinin ve ileti geçirme işlevlerinin nasıl kullanılacağı gösterilmektedir.

Bu örneği daha önceki bir ile ilişkilendirmek için `philosopher` sınıfı her `critical_section` nesnesinin her bir [eşzamanlılık:: unbounded_buffer](reference/unbounded-buffer-class.md) nesnesi ve bir `join` nesnesi kullanarak yerini alır. `join` nesnesi, philosopher 'e Chopsticks sağlayan bir Arbiter işlevi görür.

Bu örnek, bir hedef bir `unbounded_buffer` nesnesinden ileti aldığında ileti sırasından kaldırıldığı için `unbounded_buffer` sınıfını kullanır. Bu, Chopstick kullanılabilir olduğunu göstermek için ileti tutan bir `unbounded_buffer` nesnesinin kullanılmasını sağlar. İleti içermeyen bir `unbounded_buffer` nesnesi, Chopstick kullanıldığını gösterir.

Bu örnek, her iki `unbounded_buffer` nesnesi de bir ileti içerdiğinde her `philosopher` nesnesine her iki chopsticks nesnesine erişim verdiğinden, Greedy `join` olmayan bir nesne kullanır. Bir doyumsuz JOIN, iletileri kullanılabilir duruma geldiğinde kabul eden bir doyumsuz JOIN olduğundan kilitlenmeyi engellemez. Tüm doyumsuz `join` nesneleri iletilerden birini alıyorsa ve diğerinin kullanılabilir hale gelmesini bekleyene kadar kilitlenme meydana gelebilir.

Doyumsuz ve doyumsuz olmayan birleşimler ve çeşitli ileti arabelleği türleri arasındaki farklar hakkında daha fazla bilgi için bkz. [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

### <a name="to-prevent-deadlock-in-this-example"></a>Bu örnekte kilitlenmeyi önlemek için

1. Örnekteki aşağıdaki kodu kaldırın.

[!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_2.cpp)]

1. `philosopher` sınıfının `_left` ve `_right` veri üyelerinin türünü `unbounded_buffer`olarak değiştirin.

[!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_3.cpp)]

1. `philosopher` oluşturucusunu, parametreleri olarak `unbounded_buffer` nesneleri alacak şekilde değiştirin.

[!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_4.cpp)]

1. `pickup_chopsticks` yöntemini, her iki chopsticks için ileti arabelleklerinden ileti almak üzere Greedy `join` nesnesini kullanacak şekilde değiştirin.

[!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_5.cpp)]

1. `putdown_chopsticks` yöntemini, her ikisi için de ileti arabelleklerine bir ileti göndererek Chopsticks 'e erişimi serbest bırakmak için değiştirin.

[!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_6.cpp)]

1. `run` yöntemini `pickup_chopsticks` yönteminin sonuçlarını tutacak şekilde değiştirin ve bu sonuçları `putdown_chopsticks` metoduna geçirin.

[!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_7.cpp)]

1. `wmain` işlevindeki `chopsticks` değişkeninin bildirimini her biri bir ileti tutan `unbounded_buffer` nesnelerinin bir dizisi olacak şekilde değiştirin.

[!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_8.cpp)]

### <a name="description"></a>Açıklama

Aşağıda, kilitlenme riskini ortadan kaldırmak için doyumsuz olmayan `join` nesneleri kullanan tamamlanmış örnek gösterilmektedir.

### <a name="example"></a>Örnek

[!code-cpp[concrt-philosophers-join#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_9.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
aristotle ate 50 times.
descartes ate 50 times.
hobbes ate 50 times.
socrates ate 50 times.
plato ate 50 times.
```

### <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `philosophers-join.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc Philosophers-Join. cpp**

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
[Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)
