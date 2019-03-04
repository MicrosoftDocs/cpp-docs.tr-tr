---
title: 'Nasıl yapılır: Özel durum paralel bir döngüden kurtulmak için işlemeyi kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- search algorithm, writing [Concurrency Runtime]
- writing a search algorithm [Concurrency Runtime]
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
ms.openlocfilehash: 19d732d98f24172471d96cd5e2962b2a99ab0203
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262317"
---
# <a name="how-to-use-exception-handling-to-break-from-a-parallel-loop"></a>Nasıl yapılır: Özel durum paralel bir döngüden kurtulmak için işlemeyi kullanma

Bu konu, temel ağaç yapısı için bir arama algoritması yazma işlemi gösterilmektedir.

Konu [iptal](cancellation-in-the-ppl.md) paralel desen Kitaplığı'ndaki iptal rolünü açıklar. Özel durum işleme kullanımını daha paralel işi iptal etmek için daha az verimli bir şekilde kullanımıdır [concurrency::task_group::cancel](reference/task-group-class.md#cancel) ve [CONCURRENCY::structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) yöntemleri. Görevler veya paralel algoritmalar kullanır ancak sağlamaz bir üçüncü taraf kitaplığına çağırdığınızda ancak, özel durum işleme işi iptal etmek için kullanımını olduğu uygun bir senaryodur bir `task_group` veya `structured_task_group` iptal etmek için nesne.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir temel gösterir `tree` veri öğesinin ve alt düğümlerin listesini içeren bir tür. Aşağıdaki bölümde gövdesinin gösterir `for_all` yöntemi, art arda, her bir alt düğümde bir iş işlevi gerçekleştirir.

[!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği `for_all` yöntemi. Kullandığı [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) her düğümde ağacı paralel bir iş işlevi gerçekleştirmek için algoritma.

[!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği `search_for_value` belirtilen bir değeri arar işlevi `tree` nesne. Bu işleve geçirir `for_all` sağlanan değer içeren bir ağaç düğümü bulduğunda oluşturan iş işlevi bir yöntem.

Varsayımında `tree` sınıfı bir üçüncü taraf kitaplığı tarafından sağlanan ve üzerinde değişiklik yapamazsınız. Bu durumda, özel durum işleme kullanmak uygundur çünkü `for_all` yöntemi sağlamaz bir `task_group` veya `structured_task_group` çağırana nesne. Bu nedenle, iş işlevi doğrudan kendi üst görev grubunu iptal etmek silemiyor.

Bir görev grubuna sağladığınız çalışma işlevi bir özel durum oluşturduğunda, çalışma zamanı (herhangi bir alt görev grupları dahil) görev grubu içinde olan tüm görevleri durdurur ve henüz başlamamış herhangi bir görevi atar. `search_for_value` İşlevini kullanan bir `try` - `catch` bloğu özel durumu yakalayıp sonucu konsola yazdırır.

[!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnek, oluşturur bir `tree` nesne ve paralel değerlerden arar. `build_tree` İşlevi bu konunun ilerleyen bölümlerinde gösterilmektedir.

[!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]

Bu örnekte [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmasını paralel değerlerde arayın. Bu algoritma hakkında daha fazla bilgi için bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="example"></a>Örnek

Aşağıdaki tam bir örnek değerler temel ağaç yapısında aramak için özel durum işleme kullanır.

[!code-cpp[concrt-task-tree-search#5](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_5.cpp)]

Bu örnek, aşağıdaki örnek çıktısı üretir.

```Output
Found a node with value 32614.
Found a node with value 86131.
Did not find node with value 17522.
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `task-tree-search.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc görev-ağaç-search.cpp**

## <a name="see-also"></a>Ayrıca bkz.

[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[task_group Sınıfı](reference/task-group-class.md)<br/>
[structured_task_group Sınıfı](../../parallel/concrt/reference/structured-task-group-class.md)<br/>
[parallel_for_each işlevi](reference/concurrency-namespace-functions.md#parallel_for_each)
