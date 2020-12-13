---
description: 'Daha fazla bilgi edinin: Izlenecek yol: kilitlenmeyi engellemek için birleştirmeyi kullanma'
title: 'İzlenecek yol: Kilitlenmeyi Önlemek için birleştirme kullanma'
ms.date: 04/25/2019
helpviewer_keywords:
- preventing deadlock with joins [Concurrency Runtime]
- deadlock, preventing [Concurrency Runtime]
- non-greedy joins, example
- join class, example
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
ms.openlocfilehash: b74a7cd3f5f2326bb73ece13e16be95d6677bdd0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150156"
---
# <a name="walkthrough-using-join-to-prevent-deadlock"></a>İzlenecek yol: Kilitlenmeyi Önlemek için birleştirme kullanma

Bu konuda, uygulamanızda kilitlenmeyi engellemek için [concurrency:: JOIN](../../parallel/concrt/reference/join-class.md) sınıfının nasıl kullanılacağını göstermek üzere ınmpalama filozoflar sorunu kullanılmaktadır. Bir yazılım uygulamasında, iki veya daha fazla işlem bir kaynağı her tutar ve başka bir işlemin başka bir kaynağı serbest bırakma işlemini karşılıklı olarak beklemek durumunda *kilitlenme* oluşur.

Yemek filozoflar sorunu, bir kaynak kümesi birden çok eş zamanlı işlem arasında paylaşıldığında oluşabilecek genel sorun kümesine özgü bir örnektir.

## <a name="prerequisites"></a>Önkoşullar

Bu yönergeyi başlamadan önce aşağıdaki konuları okuyun:

- [Zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)

- [İzlenecek yol: Agent-Based uygulama oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)

- [Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [İleti geçirme Işlevleri](../../parallel/concrt/message-passing-functions.md)

- [Eşitleme veri yapıları](../../parallel/concrt/synchronization-data-structures.md)

## <a name="sections"></a><a name="top"></a> Başlıklı

Bu izlenecek yol aşağıdaki bölümleri içerir:

- [Dining filozoflar sorunu](#problem)

- [Bir Naïve uygulama](#deadlock)

- [Kilitlenmeyi engellemek için birleştirmeyi kullanma](#solution)

## <a name="the-dining-philosophers-problem"></a><a name="problem"></a> Dining filozoflar sorunu

Yemek filozoflar sorunu, bir uygulamada kilitlenmenin nasıl oluştuğunu gösterir. Bu sorun, yuvarlak bir tabloda beş filozoflar sıya. Her philosopher, düşünce ve Eating arasında alternatifler. Her philosopher, komşuyla komşu ile bir Chopstick paylaşmalıdır ve sağ komşu ile başka bir Chopstick. Aşağıdaki çizimde bu düzen gösterilmektedir.

![Dining filozoflar sorunu](../../parallel/concrt/media/dining_philosophersproblem.png "Dining filozoflar sorunu")

Çıkarmak için bir philosopher iki chopsticks olmalıdır. Her philosopher yalnızca bir Chopstick barındırır ve başka bir tane bekliyorsa, hiçbir philosopher ve tüm starve.

[[Üst](#top)]

## <a name="a-nave-implementation"></a><a name="deadlock"></a> Bir Naïve uygulama

Aşağıdaki örnek, Naïve filozoflar sorununun bir uygulamasını gösterir. `philosopher` [Concurrency:: Agent](../../parallel/concrt/reference/agent-class.md)' den türetilen sınıf, her philosopher bağımsız olarak hareket etmesini sağlar. Örnek, her nesneye bir Chopsticks çiftine erişim sağlamak için bir [eşzamanlılık:: critical_section](../../parallel/concrt/reference/critical-section-class.md) nesneleri paylaşılan dizisini kullanır `philosopher` .

Uygulamanın çizim ile ilişkilendirilmesi için, `philosopher` sınıfı bir philosopher temsil eder. Bir **`int`** değişken her Chopstick temsil eder. `critical_section`Nesneler, Chopsticks Rest 'in bulunduğu sahiplerini olarak görev yapar. `run`Yöntemi, philosopher ömrünü taklit eder. `think`Yöntemi, düşünce Yasası taklit eder ve yöntemi, `eat` bir dizi harekete benzetir.

Bir `philosopher` nesne, `critical_section` yöntemi çağırmadan önce Chopsticks 'in, sahiplerini kaldırma benzetimi için her iki nesneyi de kilitler `eat` . Çağrısı yapıldıktan sonra `eat` `philosopher` nesnesi, `critical_section` nesneleri kilitlenmemiş duruma geri ayarlayarak Chopsticks sahiplerini döndürür.

`pickup_chopsticks`Yöntemi, kilitlenmenin nerede gerçekleşebileceğini gösterir. Her `philosopher` nesne kilitlenmesiz birine erişirse, `philosopher` diğer kilit başka bir nesne tarafından denetlendiği için herhangi bir nesne devam edebilir `philosopher` .

### <a name="example"></a>Örnek

[!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_1.cpp)]

### <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `philosophers-deadlock.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Philosophers-Deadlock. cpp**

[[Üst](#top)]

## <a name="using-join-to-prevent-deadlock"></a><a name="solution"></a> Kilitlenmeyi engellemek için birleştirmeyi kullanma

Bu bölümde, kilitlenme olasılığını ortadan kaldırmak için ileti arabelleklerinin ve ileti geçirme işlevlerinin nasıl kullanılacağı gösterilmektedir.

Bu örneği daha önceki bir ile ilişkilendirmek için, `philosopher` sınıfı her `critical_section` nesnenin bir [eşzamanlılık:: unbounded_buffer](reference/unbounded-buffer-class.md) nesnesi ve bir nesnesi kullanarak yerini alır `join` . `join`Nesnesi, Chopsticks philosopher sağlayan bir Arbiter işlevi görür.

Bu örnek, `unbounded_buffer` bir hedef nesnesinden bir ileti aldığında ileti `unbounded_buffer` sırasından kaldırıldığında, sınıfını kullanır. Bu `unbounded_buffer` , Chopstick kullanılabilir olduğunu göstermek için ileti tutan bir nesne sağlar. `unbounded_buffer`İleti içermeyen bir nesne, Chopstick kullanıldığını gösterir.

Bu örnek, `join` her `philosopher` iki nesne de bir ileti içerdiğinde her bir nesneye yalnızca Chopsticks için her nesne erişimini sağladığından Greedy olmayan bir nesne kullanır `unbounded_buffer` . Bir doyumsuz JOIN, iletileri kullanılabilir duruma geldiğinde kabul eden bir doyumsuz JOIN olduğundan kilitlenmeyi engellemez. Tüm doyumsuz `join` nesneleri iletilerden birini alıyorsa ve sürekli diğerinin kullanılabilir hale gelmesini bekleyene kilitlenme meydana gelebilir.

Doyumsuz ve doyumsuz olmayan birleşimler ve çeşitli ileti arabelleği türleri arasındaki farklar hakkında daha fazla bilgi için bkz. [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

### <a name="to-prevent-deadlock-in-this-example"></a>Bu örnekte kilitlenmeyi önlemek için

1. Örnekteki aşağıdaki kodu kaldırın.

[!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_2.cpp)]

1. `_left` `_right` Sınıfının ve veri üyelerinin türünü `philosopher` olarak değiştirin `unbounded_buffer` .

[!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_3.cpp)]

1. Oluşturucuyu, `philosopher` `unbounded_buffer` parametreleri olarak nesneler alacak şekilde değiştirin.

[!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_4.cpp)]

1. Yöntemi, `pickup_chopsticks` `join` hem Chopsticks hem de ileti arabelleklerinden ileti almak için, Greedy olmayan bir nesne kullanmak üzere değiştirin.

[!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_5.cpp)]

1. `putdown_chopsticks`Her iki chopsticks için ileti arabelleklerine bir ileti göndererek Chopsticks erişimini serbest bırakma yöntemini değiştirin.

[!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_6.cpp)]

1. Yöntemi, yönteminin `run` sonuçlarını tutacak şekilde değiştirin `pickup_chopsticks` ve bu sonuçları `putdown_chopsticks` metoduna geçirin.

[!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_7.cpp)]

1. `chopsticks`İşlevindeki değişkenin bildirimini, `wmain` `unbounded_buffer` her birinin bir ileti tutan bir nesne dizisi olacak şekilde değiştirin.

[!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_8.cpp)]

### <a name="description"></a>Açıklama

Aşağıda, `join` kilitlenme riskini ortadan kaldırmak için doyumsuz olmayan nesneleri kullanan tamamlanmış örnek gösterilmektedir.

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

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `philosophers-join.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Philosophers-Join. cpp**

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı Izlenecek yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)<br/>
[Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti geçirme Işlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
[Eşitleme veri yapıları](../../parallel/concrt/synchronization-data-structures.md)
