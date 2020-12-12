---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: paralel sıralama yordamı yazmak için parallel_invoke kullanma'
title: 'Nasıl yapılır: Paralel Sıralama Rutini Yazmak için parallel_invoke Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- task_handle class, example
- task_group class, example
- make_task function, example
- structured_task_group class, example
- improving parallel performance with task groups [Concurrency Runtime]
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
ms.openlocfilehash: 4146bed939e265f611d79c465681c10ef28a1ebe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205684"
---
# <a name="how-to-use-parallel_invoke-to-write-a-parallel-sort-routine"></a>Nasıl yapılır: Paralel Sıralama Rutini Yazmak için parallel_invoke Kullanma

Bu belgede, bitonic sıralama algoritmasının performansını geliştirmek için [parallel_invoke](../../parallel/concrt/parallel-algorithms.md#parallel_invoke) algoritmasının nasıl kullanılacağı açıklanmaktadır. Bitonic sıralama algoritması, giriş dizisini yinelemeli olarak daha küçük sıralı bölümlere ayırır. Her bölüm işlemi diğer işlemlerden bağımsız olduğu için bitonic sıralama algoritması paralel olarak çalıştırılabilir.

Bitonic sıralaması, giriş sıralarının tüm birleşimlerini sıralayan bir *sıralama ağı* örneği olsa da bu örnek, uzunlukları ikinin üssü olan dizileri sıralar.

> [!NOTE]
> Bu örnek, çizim için bir paralel sıralama yordamı kullanır. Ayrıca, PPL 'nin sağladığı yerleşik sıralama algoritmalarından de yararlanabilirsiniz: [eşzamanlılık::p arallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [eşzamanlılık::p arallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort)ve [eşzamanlılık::p arallel_radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="sections"></a><a name="top"></a> Başlıklı

Bu belgede aşağıdaki görevler açıklanmaktadır:

- [Bitonic sıralama hizmeti gerçekleştiriliyor](#serial)

- [Paralel olarak Sırtonic sıralama gerçekleştirmek için parallel_invoke kullanma](#parallel)

## <a name="performing-bitonic-sort-serially"></a><a name="serial"></a> Bitonic sıralama hizmeti gerçekleştiriliyor

Aşağıdaki örnek, bitonic sıralama algoritmasının seri sürümünü gösterir. `bitonic_sort`İşlevi, diziyi iki bölüme böler, bu bölümleri karşıt yönlere göre sıralar ve sonra sonuçları birleştirir. Bu işlev, her bölümü sıralamak için iki kez yinelemeli olarak çağırır.

[!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]

[[Üst](#top)]

## <a name="using-parallel_invoke-to-perform-bitonic-sort-in-parallel"></a><a name="parallel"></a> Paralel olarak Sırtonic sıralama gerçekleştirmek için parallel_invoke kullanma

Bu bölümde, `parallel_invoke` bıtonic sıralama algoritmasını paralel olarak gerçekleştirmek için algoritmanın nasıl kullanılacağı açıklanmaktadır.

### <a name="to-perform-the-bitonic-sort-algorithm-in-parallel"></a>Paralel olarak bitonic sıralama algoritmasını gerçekleştirmek için

1. `#include`PPL. h üstbilgi dosyası için bir yönerge ekleyin.

[!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]

1. **`using`** Ad alanı için bir yönerge ekleyin `concurrency` .

[!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]

1. `parallel_bitonic_mege` `parallel_invoke` İş için yeterli miktarda çalışma miktarı varsa, dizileri paralel olarak birleştirmek için algoritması kullanan yeni bir işlev oluşturun. Aksi takdirde, `bitonic_merge` dizileri seri olarak birleştirmek için çağırın.

[!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]

1. Önceki adımda, ancak işlevi için benzeyen bir işlem gerçekleştirin `bitonic_sort` .

[!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]

1. `parallel_bitonic_sort`İşlevin diziyi artan sırada sıralayan aşırı yüklenmiş bir sürümünü oluşturun.

[!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]

`parallel_invoke`Algoritma, çağırma bağlamındaki görev dizisinin son kısmını gerçekleştirerek yükü azaltır. Örneğin, `parallel_bitonic_sort` işlevinde, ilk görev ayrı bir bağlam üzerinde çalışır ve ikinci görev çağıran bağlam üzerinde çalışır.

[!code-cpp[concrt-parallel-bitonic-sort#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_7.cpp)]

Aşağıdaki tüm örnek, hem seri hem de bitonic sıralama algoritmasının paralel sürümlerini gerçekleştirir. Örnek ayrıca konsola her hesaplamayı gerçekleştirmek için gereken zamanı da yazdırır.

[!code-cpp[concrt-parallel-bitonic-sort#8](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_8.cpp)]

Aşağıdaki örnek çıktı, dört işlemcili bir bilgisayar içindir.

```Output
serial time: 4353
parallel time: 1248
```

[[Üst](#top)]

### <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `parallel-bitonic-sort.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Parallel-bitonic-Sort. cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Bu örnek `parallel_invoke` [eşzamanlılık:: task_group](reference/task-group-class.md) sınıfı yerine algoritmayı kullanır, çünkü her görev grubunun ömrü bir işlevin ötesine genişlemez. `parallel_invoke`Daha az yürütme yüküne sahip olduğundan `task group` ve daha sonra, daha iyi performans sağlayan kod yazmanıza olanak sağladığından kullanmanızı öneririz.

Bazı algoritmaların paralel sürümleri, yalnızca yapmak için yeterli iş olduğunda daha iyi gerçekleştirilir. Örneğin, `parallel_bitonic_merge` `bitonic_merge` dizide 500 veya daha az öğe varsa, bu işlev seri sürümünü çağırır. Ayrıca, çalışma miktarına göre Genel sıralama stratejinizi planlayabilirsiniz. Örneğin, aşağıdaki örnekte gösterildiği gibi, dizi 500 öğeden az öğe içeriyorsa hızlı sıralama algoritmasının seri sürümünü kullanmak daha verimli olabilir:

[!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]

Tüm paralel algoritmaların yanı sıra, kodunuzun uygun şekilde profilini oluşturup ayarlamanız önerilir.

## <a name="see-also"></a>Ayrıca bkz.

[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[parallel_invoke Işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)
