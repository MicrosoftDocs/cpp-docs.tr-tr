---
title: Paralel Desen Kitaplığı (PPL)
ms.date: 11/04/2016
helpviewer_keywords:
- Parallel Patterns Library (PPL)
ms.assetid: 40fd86b2-69fa-45e5-93d8-98a75636c242
ms.openlocfilehash: deeede132a919084399be54d5559605b99c4e4fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459416"
---
# <a name="parallel-patterns-library-ppl"></a>Paralel Desen Kitaplığı (PPL)

Paralel Desen kitaplığı (PPL), ölçeklenebilirlik ve kolayca eş zamanlı uygulamalar geliştirmeye yönelik kullanım yükseltir zorunlu programlama modeli sağlar. PPL, zamanlama ve kaynak yönetimi bileşenlerine eşzamanlılık çalışma zamanı oluşturur. Paralel veri çubuğunda genel, tür kullanımı uyumlu algoritmalar ve hareket kapsayıcılar sağlayarak uygulama kodunuzu ve temel iş parçacığı mekanizması arasında soyutlama düzeyinde yükseltir. PPL de paylaşılan durum alternatifleri sağlayarak ölçeklendirilen uygulamalar geliştirmenize olanak tanır.

PPL, aşağıdaki özellikleri sağlar:

- *Görev Paralelliği*: bazı iş öğeleri (Görevler) paralel olarak yürütmek için Windows iş parçacığı havuzu üzerinde çalışan bir mekanizma

- *Paralel algoritmalar*: eşzamanlılık yapacak çalışma zamanı üzerinde paralel veri koleksiyonlarının çalışır genel algoritmalar

- *Paralel kapsayıcılar ve nesneler*: öğelerini eşzamanlı güvenli erişim sağlayan genel kapsayıcı türleri

## <a name="example"></a>Örnek

PPL, C++ Standart Kitaplığı benzeyen bir programlama modeli sağlar. Aşağıdaki örnek PPL birçok özelliklerini gösterir. Seri olarak ve paralel birkaç Fibonacci sayı hesaplar. Her iki hesaplamalar üzerinde işlem bir [std::array](../../standard-library/array-class-stl.md) nesne. Örnek ayrıca, her iki hesaplamalar gerçekleştirmek için gerekli olduğu süre konsola yazdırır.

C++ Standart Kitaplığı seri sürümü kullanan [std::for_each](../../standard-library/algorithm-functions.md#for_each) dizi geçirmek için algoritma ve sonuçlarda depolar bir [std::vector](../../standard-library/vector-class.md) nesne. Paralel sürüm aynı görevi gerçekleştirir, ancak PPL kullanan [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritması ve sonuçlarda depolayan bir [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) nesne. `concurrent_vector` Eşzamanlı olarak kapsayıcıya yazma erişimi eşitleme gereksinimini olmadan öğeleri eklemek, her döngü tekrarında sınıfı sağlar.

Çünkü `parallel_for_each` paralel sürümü bu örnek, aynı anda sıralama gerekir davranır `concurrent_vector` seri sürümü aynı sonuçları üretmek için nesne.

Örnek Fibonacci sayıları hesaplamak için naïve yöntemi kullandığına dikkat edin; Ancak, bu yöntem, eşzamanlılık çalışma zamanı uzun hesaplamalar performansını nasıl geliştireceğiniz gösterilmektedir.

[!code-cpp[concrt-parallel-fibonacci#1](../../parallel/concrt/codesnippet/cpp/parallel-patterns-library-ppl_1.cpp)]

Aşağıdaki örnek çıktıda dört işlemciye sahip bir bilgisayar içindir.

```Output
serial time: 9250 ms
parallel time: 5726 ms

fib(24): 46368
fib(26): 121393
fib(41): 165580141
fib(42): 267914296
```

Döngünün her yinelemesinden tamamlamak için farklı bir süre gerektirir. Performansını `parallel_for_each` son sona eren işlemi tarafından sınırlıdır. Bu nedenle, bu örnekte seri ve paralel sürümleri arasında doğrusal performans iyileştirmeleri beklememeniz gerekir.

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|Görevler ve görev grupları ppl'de rolünü açıklar.|
|[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)|Paralel algoritmalar gibi kullanmayı açıklar `parallel_for` ve `parallel_for_each`.|
|[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)|Çeşitli paralel kapsayıcılar ve ppl Yapıları tarafından sağlanan nesneler açıklar.|
|[PPL'de İptal](cancellation-in-the-ppl.md)|Bir paralel algoritma tarafından gerçekleştirilen işi iptal etmek açıklanmaktadır.|
|[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)|Eşzamanlılık paralel programlama basitleştirir ve ilgili konulara bağlantılar içeren çalışma zamanı, açıklar.|

