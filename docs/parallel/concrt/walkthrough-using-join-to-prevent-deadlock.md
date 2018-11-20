---
title: 'İzlenecek yol: Kilitlenmeyi Önlemek için birleştirme kullanma'
ms.date: 11/19/2018
helpviewer_keywords:
- preventing deadlock with joins [Concurrency Runtime]
- deadlock, preventing [Concurrency Runtime]
- non-greedy joins, example
- join class, example
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
ms.openlocfilehash: b62f4007a79faaff479e4e8ff998a8b48e4d5dd1
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175927"
---
# <a name="walkthrough-using-join-to-prevent-deadlock"></a>İzlenecek yol: Kilitlenmeyi Önlemek için birleştirme kullanma

Bu konuda yemek Yiyen Filozoflar sorunu nasıl kullanılacağını örneklendiren kullanmasını [concurrency::join](../../parallel/concrt/reference/join-class.md) uygulamanızdaki kilitlenmeyi önlemek için sınıf. Bir yazılım uygulamasındaki *kilitlenme* iki veya daha fazla işlem her bir kaynak basılı tutun ve karşılıklı olarak başka bir kaynağı serbest bırakmak başka bir işlemin tamamlanmasını beklemek oluşur.

Yemek Yiyen Filozoflar sorunu, genel bir kaynak kümesini birden çok eşzamanlı işlemler arasında paylaşıldığında ortaya çıkabilecek sorunları kümesinin belirli bir örnektir.

## <a name="prerequisites"></a>Önkoşullar

Bu kılavuza başlamadan önce aşağıdaki konuları okuyun:

- [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)

- [İzlenecek Yol: Aracı Temelli Uygulama Oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)

- [Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)

##  <a name="top"></a> Bölümleri

Bu izlenecek yol aşağıdaki bölümleri içerir:

- [Yemek Yiyen Filozoflar sorunu](#problem)

- [Naïve uygulama](#deadlock)

- [Kilitlenmeyi önlemek için birleştirme kullanma](#solution)

##  <a name="problem"></a> Yemek Yiyen Filozoflar sorunu

Yemek Yiyen Filozoflar sorunu kilitlenme bir uygulamada nasıl gerçekleştirildiğini gösterir. Bu sorunda bir gidiş tablosunu beş Yiyen Filozoflar yaslanın. Her filozof düşünmek ve yemek arasında geçiş yapıyor. Her filozof ile komşu sola ve başka bir chopstick paylaşmalıdır chopstick sağa komşu ile. Bu düzeni aşağıdaki çizimde gösterilmektedir.

![Yemek Yiyen Filozoflar sorunu](../../parallel/concrt/media/dining_philosophersproblem.png "yemek Yiyen Filozoflar sorunu")

Yemek için bir filozof iki chopsticks tutmanız gerekir. Her filozof tek chopstick tutar ve için başka bir bekleyen, ardından hiçbir filozof yemek ve tüm yeterli kaynak kalmamasına neden.

[[Üst](#top)]

##  <a name="deadlock"></a> Naïve uygulama

Aşağıdaki örnek, Yemek Yiyen Filozoflar sorunu naïve uygulanışı gösterilmektedir. `philosopher` Türetilen sınıf [concurrency::agent](../../parallel/concrt/reference/agent-class.md), bağımsız olarak işlem her filozof sağlar. Paylaşılan bir dizi örnekte [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) her vermek için nesneleri `philosopher` nesne chopsticks çiftinin özel erişim.

Uygulamaya gösterim ilişkilendirilecek `philosopher` sınıfı bir filozof temsil eder. Bir `int` değişken her chopstick temsil eder. `critical_section` Nesneleri üzerinde chopsticks rest sahipleri hizmet eder. `run` Yöntemi filozof ömrünü benzetimini yapar. `think` Yöntemi düşünce Yasası benzetimini yapar ve `eat` yöntemi yemek eylemi benzetimini yapar.

A `philosopher` nesne hem de kilitler `critical_section` sahiplerini kendisinden önce gelen chopsticks kaldırılmasını benzetimini yapmak için çağırdığı nesneleri `eat` yöntemi. Çağrısından sonra `eat`, `philosopher` nesnesi döndüren chopsticks üstlenenlere ayarlayarak `critical_section` nesneleri geri kilidi durumu.

`pickup_chopsticks` Yöntemi gösterir burada Kilitlenme ortaya çıkabilir. Her varsa `philosopher` nesne kilitler birini ve ardından Hayır erişim kazanır `philosopher` diğer kilit bir başkası tarafından denetlenir çünkü nesne devam edebilir `philosopher` nesne.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

### <a name="code"></a>Kod

[!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_1.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `philosophers-deadlock.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc Yiyen Filozoflar deadlock.cpp**

[[Üst](#top)]

##  <a name="solution"></a> Kilitlenmeyi önlemek için birleştirme kullanma

Bu bölümde, kilitlenme olasılığını ortadan kaldırmak için mesaj arabellekleri ve ileti geçirme işlevleri kullanma gösterilir.

Bu örnek önceki bir ilişkilendirmek için `philosopher` sınıfı her değiştirir `critical_section` kullanarak nesneyi bir [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) nesnesi ve bir `join` nesne. `join` Nesne için filozof chopsticks sağlayan bir arbiter görür.

Bu örnekte `unbounded_buffer` bir hedefe bir ileti aldığında çünkü bir `unbounded_buffer` nesnesi, iletiyi, ileti sırasından kaldırılır. Böylece bir `unbounded_buffer` chopstick olduğunu belirten bir ileti tutan nesne kullanılabilir. Bir `unbounded_buffer` ileti tutan nesne chopstick kullanılmakta olduğunu gösterir.

Bu örnekte bir doyumsuz olmayan `join` doyumsuz olmayan birleştirme her sağladığından nesne `philosopher` nesne iki chopsticks erişimi yalnızca her ikisi de `unbounded_buffer` nesneleri içeren bir ileti. Kullanılabilir olduklarında hemen sonra doyumsuz birleştirme iletileri kabul ettiğinden, doyumsuz birleştirme kilitlenme engellemez. Kilitlenme tüm doyumsuz değilse oluşabilir `join` nesneler iletilerinden birini alabilirsiniz, ancak sonsuza kadar diğer kullanılabilir olana kadar bekleyin.

Doyumsuz ve doyumsuz olmayan birleştirmeler ve çeşitli ileti arabelleği türleri arasındaki farklar hakkında daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

#### <a name="to-prevent-deadlock-in-this-example"></a>Bu örnekte kilitlenmeyi önlemek için

1. Aşağıdaki kod örneğinden kaldırın.

[!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_2.cpp)]

1. Türünü değiştirme `_left` ve `_right` veri üyeleri `philosopher` sınıfının `unbounded_buffer`.

[!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_3.cpp)]

1. Değiştirme `philosopher` gerçekleştirilecek Oluşturucusu `unbounded_buffer` , parametre olarak nesne.

[!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_4.cpp)]

1. Değiştirme `pickup_chopsticks` yöntemi bir doyumsuz olmayan `join` ileti arabellekleri için her iki chopsticks iletileri alacak şekilde nesne.

[!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_5.cpp)]

1. Değiştirme `putdown_chopsticks` ileti arabellekleri için her iki chopsticks bir ileti göndererek chopsticks erişimi serbest bırakmak için yöntemi.

[!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_6.cpp)]

1. Değiştirme `run` sonuçlarını tutmak için yöntemi `pickup_chopsticks` yöntemi ve bu sonuçları geçirilecek `putdown_chopsticks` yöntemi.

[!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_7.cpp)]

1. Değiştirin `chopsticks` değişkeninde `wmain` işlevi bir dizi `unbounded_buffer` nesneleri her bir ileti tutun.

[!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_8.cpp)]

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki kullanan tamamlanan örnek doyumsuz olmayan gösterir `join` kilitlenmesi riskini ortadan kaldırmak için nesne.

### <a name="code"></a>Kod

[!code-cpp[concrt-philosophers-join#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_9.cpp)]

### <a name="comments"></a>Açıklamalar

Bu örnek aşağıdaki çıktıyı üretir.

```Output
aristotle ate 50 times.
descartes ate 50 times.
hobbes ate 50 times.
socrates ate 50 times.
plato ate 50 times.
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `philosophers-join.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc Yiyen Filozoflar join.cpp**

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
[Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)
