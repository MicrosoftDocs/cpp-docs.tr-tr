---
title: 'Nasıl yapılır: Paralel Sıralama Rutini Yazmak için parallel_invoke Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- task_handle class, example
- task_group class, example
- make_task function, example
- structured_task_group class, example
- improving parallel performance with task groups [Concurrency Runtime]
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
ms.openlocfilehash: 6acac3f6bc82db6e6981f83715c7ee88cfd06fbd
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855414"
---
# <a name="how-to-use-parallel_invoke-to-write-a-parallel-sort-routine"></a>Nasıl yapılır: Paralel Sıralama Rutini Yazmak için parallel_invoke Kullanma

Bu belgede, bitonic sıralama algoritmasının performansını geliştirmek için [parallel_invoke](../../parallel/concrt/parallel-algorithms.md#parallel_invoke) algoritmasının nasıl kullanılacağı açıklanmaktadır. Bitonic sıralama algoritması, giriş dizisini yinelemeli olarak daha küçük sıralı bölümlere ayırır. Her bölüm işlemi diğer işlemlerden bağımsız olduğu için bitonic sıralama algoritması paralel olarak çalıştırılabilir.

Bitonic sıralaması, giriş sıralarının tüm birleşimlerini sıralayan bir *sıralama ağı* örneği olsa da bu örnek, uzunlukları ikinin üssü olan dizileri sıralar.

> [!NOTE]
> Bu örnek, çizim için bir paralel sıralama yordamı kullanır. Ayrıca, PPL 'nin sağladığı yerleşik sıralama algoritmalarından de yararlanabilirsiniz: [eşzamanlılık::p arallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [eşzamanlılık::p arallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort)ve [eşzamanlılık::p arallel_radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="top"></a>Başlıklı

Bu belgede aşağıdaki görevler açıklanmaktadır:

- [Bitonic sıralama hizmeti gerçekleştiriliyor](#serial)

- [Paralel olarak Sırtonic sıralama gerçekleştirmek için parallel_invoke kullanma](#parallel)

## <a name="serial"></a>Bitonic sıralama hizmeti gerçekleştiriliyor

Aşağıdaki örnek, bitonic sıralama algoritmasının seri sürümünü gösterir. `bitonic_sort` işlevi diziyi iki bölüme böler, bu bölümleri karşıt yönlere göre sıralar ve sonra sonuçları birleştirir. Bu işlev, her bölümü sıralamak için iki kez yinelemeli olarak çağırır.

[!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]

[[Üst](#top)]

## <a name="parallel"></a>Paralel olarak Sırtonic sıralama gerçekleştirmek için parallel_invoke kullanma

Bu bölümde, bıtonic sıralama algoritmasını paralel olarak gerçekleştirmek için `parallel_invoke` algoritmasının nasıl kullanılacağı açıklanmaktadır.

### <a name="to-perform-the-bitonic-sort-algorithm-in-parallel"></a>Paralel olarak bitonic sıralama algoritmasını gerçekleştirmek için

1. PPL. h üstbilgi dosyası için bir `#include` yönergesi ekleyin.

[!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]

1. `concurrency` ad alanı için bir `using` yönergesi ekleyin.

[!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]

1. `parallel_bitonic_mege`adlı yeni bir işlev oluşturun, bu, yapmak için yeterli miktarda iş olması durumunda dizileri paralel olarak birleştirmek için `parallel_invoke` algoritmasını kullanır. Aksi takdirde, dizileri seri olarak birleştirmek için `bitonic_merge` çağırın.

[!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]

1. Önceki adımda olduğu gibi, ancak `bitonic_sort` işlevi için bir işlem gerçekleştirin.

[!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]

1. Diziyi artan sırada sıralayan `parallel_bitonic_sort` işlevinin aşırı yüklenmiş bir sürümünü oluşturun.

[!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]

`parallel_invoke` algoritması, çağırma bağlamındaki görev dizisinin son kısmını gerçekleştirerek yükü azaltır. Örneğin, `parallel_bitonic_sort` işlevinde, ilk görev ayrı bir bağlam üzerinde çalışır ve ikinci görev çağıran bağlam üzerinde çalışır.

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

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya `parallel-bitonic-sort.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc Parallel-bitonic-Sort. cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Bu örnek, her görev grubunun ömrü bir işlevin ötesinde genişlemediğinden [eşzamanlılık:: task_group](reference/task-group-class.md) sınıfı yerine `parallel_invoke` algoritmasını kullanır. `task group` nesnelerinden daha az yürütme yüküne sahip olduğundan `parallel_invoke` kullanmanızı öneririz ve bu nedenle daha iyi bir performans sağlayan kod yazmanızı sağlar.

Bazı algoritmaların paralel sürümleri, yalnızca yapmak için yeterli iş olduğunda daha iyi gerçekleştirilir. Örneğin, `parallel_bitonic_merge` işlevi, dizide 500 veya daha az öğe varsa `bitonic_merge`seri sürümünü çağırır. Ayrıca, çalışma miktarına göre Genel sıralama stratejinizi planlayabilirsiniz. Örneğin, aşağıdaki örnekte gösterildiği gibi, dizi 500 öğeden az öğe içeriyorsa hızlı sıralama algoritmasının seri sürümünü kullanmak daha verimli olabilir:

[!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]

Tüm paralel algoritmaların yanı sıra, kodunuzun uygun şekilde profilini oluşturup ayarlamanız önerilir.

## <a name="see-also"></a>Ayrıca bkz.

[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[parallel_invoke Işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)
