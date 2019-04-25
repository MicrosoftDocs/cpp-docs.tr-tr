---
title: 'Nasıl yapılır: Paralel sıralama rutini yazmak için parallel_invoke kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- task_handle class, example
- task_group class, example
- make_task function, example
- structured_task_group class, example
- improving parallel performance with task groups [Concurrency Runtime]
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
ms.openlocfilehash: 329cf275f283ba7b57276d06e909905c9a900697
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252938"
---
# <a name="how-to-use-parallelinvoke-to-write-a-parallel-sort-routine"></a>Nasıl yapılır: Paralel sıralama rutini yazmak için parallel_invoke kullanma

Bu belgenin nasıl kullanılacağını açıklar [parallel_invoke](../../parallel/concrt/parallel-algorithms.md#parallel_invoke) bitonic sıralama algoritmasının performansını artırmak için algoritma. Bitonic sıralama algoritmasını yinelemeli olarak Giriş dizisinin küçük sıralanmış bölümlere böler. Her bölüm işlemi tüm diğer işlemlerden bağımsız olduğundan paralel olarak bitonic sıralama algoritmasının çalıştırabilirsiniz.

Örnek olarak bitonic sıralama olmasına rağmen bir *ağ sıralama* , tüm giriş dizilerini birleşimlerini sıralar, bu örnek, uzunlukları ikinin kuvveti olan dizileri sıralar.

> [!NOTE]
>  Bu örnek bir paralel sıralama rutini gösterim amacıyla kullanır. PPL sağlayan yerleşik sıralama algoritmaları de kullanabilirsiniz: [concurrency::parallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [concurrency::parallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort), ve [concurrency::parallel_ radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Daha fazla bilgi için [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

##  <a name="top"></a> Bölümleri

Bu belgede, aşağıdaki görevleri açıklanmaktadır:

- [Seri olarak Bitonic sıralamayı gerçekleştirme](#serial)

- [Paralel olarak Bitonic sıralama için parallel_invoke kullanma](#parallel)

##  <a name="serial"></a> Seri olarak Bitonic sıralamayı gerçekleştirme

Aşağıdaki örnek bitonic sıralama algoritmasının seri sürümünü gösterir. `bitonic_sort` İşlevi dizisi iki bölüme ayıran, o bölümler ters yönlerde sıralar ve ardından sonuçları birleştirir. Bu işlev, kendisi her bölüm sıralamak için iki kez yinelemeli olarak çağırır.

[!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]

[[Üst](#top)]

##  <a name="parallel"></a> Paralel olarak Bitonic sıralama için parallel_invoke kullanma

Bu bölümde, nasıl kullanılacağını açıklar `parallel_invoke` paralel olarak bitonic sıralama algoritmasını gerçekleştirmek için kullanılan algoritma.

### <a name="procedures"></a>Yordamlar

##### <a name="to-perform-the-bitonic-sort-algorithm-in-parallel"></a>Paralel olarak bitonic sıralama algoritmasını gerçekleştirmek için

1. Ekleme bir `#include` üstbilgi dosyası ppl.h yönergesi.

[!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]

1. Ekleme bir `using` yönergesi `concurrency` ad alanı.

[!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]

1. Adlı yeni bir işlev oluşturma `parallel_bitonic_mege`, kullanan `parallel_invoke` dizileri paralel iş yapmak için yeterli miktarda ise birleştirme algoritması. Aksi takdirde, çağrı `bitonic_merge` dizileri seri olarak birleştirilecek.

[!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]

1. Önceki adımda, ancak için benzer bir işlemi gerçekleştirmek `bitonic_sort` işlevi.

[!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]

1. Aşırı yüklenmiş bir sürümünü oluşturmasına `parallel_bitonic_sort` dizi artan düzende sıralayan işlev.

[!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]

`parallel_invoke` Algoritması, görev dizisini son arama bağlamda gerçekleştirerek ek yükü azaltır. Örneğin, `parallel_bitonic_sort` işlevi, ilk görevi ayrı bir bağlamda çalışır ve ikinci görev çağıran bağlamını üzerinde çalışır.

[!code-cpp[concrt-parallel-bitonic-sort#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_7.cpp)]

Aşağıdaki tam bir örnek, hem seri hem de bitonic sıralama algoritmasını paralel sürümlerini gerçekleştirir. Örnek ayrıca, her bir hesaplama gerçekleştirmek için gereken süreyi konsola yazdırır.

[!code-cpp[concrt-parallel-bitonic-sort#8](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_8.cpp)]

Aşağıdaki örnek çıktıda dört işlemciye sahip bir bilgisayar içindir.

```Output
serial time: 4353
parallel time: 1248
```

[[Üst](#top)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `parallel-bitonic-sort.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe /EHsc parallel-bitonic-sort.cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Bu örnekte `parallel_invoke` algoritması yerine [concurrency::task_group](reference/task-group-class.md) çünkü her görev grubu ömrünü bir işlev kapsamaz. Kullanmanızı öneririz `parallel_invoke` yükü daha az yürütme olduğundan Yapabildiğinizde `task group` nesneleri ve bu nedenle daha iyi performans gösteren kod yazmanızı sağlar.

Yalnızca yapmak için yeterli iş olduğunda bazı algoritmalar paralel sürümlerini daha iyi performans. Örneğin, `parallel_bitonic_merge` işlevi çağırır seri sürüm `bitonic_merge`, sırayla 500 veya daha az öğe varsa. Ayrıca, iş miktarına göre Genel sıralama stratejinizi planlayabilirsiniz. Örneğin, 500'den az öğe, dizinin içeriyorsa, aşağıdaki örnekte gösterildiği gibi hızlı Sıralama algoritması seri sürümünü kullanmanız daha verimli olabilir:

[!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]

Tüm paralel algoritma olarak ile profil ve uygun şekilde kodunuzu ayarlamaya öneririz.

## <a name="see-also"></a>Ayrıca bkz.

[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[parallel_invoke işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)
