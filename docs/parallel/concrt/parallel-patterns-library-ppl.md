---
description: 'Daha fazla bilgi edinin: paralel Desenler kitaplığı (PPL)'
title: Paralel Desen Kitaplığı (PPL)
ms.date: 11/04/2016
helpviewer_keywords:
- Parallel Patterns Library (PPL)
ms.assetid: 40fd86b2-69fa-45e5-93d8-98a75636c242
ms.openlocfilehash: ea5719e8ebaacf8f181678ef7af8aae9c900fbe6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172355"
---
# <a name="parallel-patterns-library-ppl"></a>Paralel Desen Kitaplığı (PPL)

Paralel Desenler kitaplığı (PPL), eşzamanlı uygulamalar geliştirmek için ölçeklenebilirliği ve kullanım kolaylığını kolaylaştıran bir zorunlu programlama modeli sağlar. PPL, Eşzamanlılık Çalışma Zamanı zamanlama ve kaynak yönetimi bileşenlerinde oluşturulur. Paralel olarak veri üzerinde çalışan genel, tür kullanımı uyumlu algoritmalar ve kapsayıcılar sunarak, uygulama kodunuz ve temel alınan iş parçacığı mekanizması arasındaki soyutlama düzeyini yükseltir. PPL, paylaşılan duruma alternatifler sunarak ölçeklendirilen uygulamalar geliştirmenize de olanak tanır.

PPL aşağıdaki özellikleri sağlar:

- *Görev Paralelliği*: birkaç çalışma öğesini (görev) paralel olarak yürütmek Için Windows ThreadPool üzerinde çalışan bir mekanizma

- *Paralel algoritmalar*: eşzamanlılık çalışma zamanı en üstünde çalışarak paralel olarak veri koleksiyonlarına işlem yapmak için kullanılan genel algoritmalar

- *Paralel kapsayıcılar ve nesneler*: öğelerine güvenli eşzamanlı erişim sağlayan genel kapsayıcı türleri

## <a name="example"></a>Örnek

PPL, C++ standart kitaplığına benzeyen bir programlama modeli sağlar. Aşağıdaki örnek, PPL 'nin birçok özelliğini gösterir. Birkaç Fibonaccı numarasını ve paralel olarak bir şekilde hesaplar. Her iki hesaplama da bir [std:: Array](../../standard-library/array-class-stl.md) nesnesi üzerinde çalışır. Örnek ayrıca konsola her iki hesaplama da için gereken zamanı da yazdırır.

Seri sürümü dizide çapraz geçiş yapmak için C++ Standart Kitaplığı [std:: for_each](../../standard-library/algorithm-functions.md#for_each) algoritmasını kullanır ve sonuçları [std:: vector](../../standard-library/vector-class.md) nesnesinde depolar. Paralel sürüm aynı görevi gerçekleştirir, ancak PPL [eşzamanlılık::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasını kullanır ve sonuçları bir [eşzamanlılık:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) nesnesinde depolar. `concurrent_vector`Sınıfı her döngü yinelemesinin, kapsayıcıya yazma erişimini eşitlemeye gerek kalmadan eşzamanlı olarak öğe eklemesine olanak sağlar.

Aynı `parallel_for_each` anda davrandığı için, bu örneğin paralel sürümü `concurrent_vector` nesneyi seri sürümü ile aynı sonuçları üretecek şekilde sıralamalıdır.

Örneğin, Fibonaccı numaralarını hesaplamak için bir Naïve yöntemi kullandığını unutmayın; Ancak, bu yöntem Eşzamanlılık Çalışma Zamanı uzun hesaplamaların performansını nasıl geliştirebileceğinizi gösterir.

[!code-cpp[concrt-parallel-fibonacci#1](../../parallel/concrt/codesnippet/cpp/parallel-patterns-library-ppl_1.cpp)]

Aşağıdaki örnek çıktı, dört işlemcili bir bilgisayar içindir.

```Output
serial time: 9250 ms
parallel time: 5726 ms

fib(24): 46368
fib(26): 121393
fib(41): 165580141
fib(42): 267914296
```

Döngünün her yinelemesi için farklı bir süre sonu gerekir. Performansı, `parallel_for_each` son sona geçen işlem ile sınırlıdır. Bu nedenle, bu örneğin seri ve paralel sürümleri arasında doğrusal performans iyileştirmeleri beklememelisiniz.

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|PPL 'de görevlerin ve görev gruplarının rolünü açıklar.|
|[Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)|Ve gibi paralel algoritmaların nasıl kullanılacağını açıklar `parallel_for` `parallel_for_each` .|
|[Paralel Kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md)|PPL tarafından sunulan çeşitli paralel kapsayıcıları ve nesneleri açıklar.|
|[PPL'de İptal](cancellation-in-the-ppl.md)|Paralel algoritma tarafından gerçekleştirilen çalışmanın nasıl iptal edildiğini açıklar.|
|[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)|Paralel programlamayı kolaylaştıran ve ilgili konuların bağlantılarını içeren Eşzamanlılık Çalışma Zamanı açıklar.|
