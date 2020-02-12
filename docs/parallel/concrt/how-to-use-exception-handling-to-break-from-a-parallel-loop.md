---
title: 'Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için Özel Durum İşlemeyi Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- search algorithm, writing [Concurrency Runtime]
- writing a search algorithm [Concurrency Runtime]
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
ms.openlocfilehash: a5576e8f2416804cac89f5ec34005f4e08b99c47
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142109"
---
# <a name="how-to-use-exception-handling-to-break-from-a-parallel-loop"></a>Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için Özel Durum İşlemeyi Kullanma

Bu konu başlığı altında, temel ağaç yapısına yönelik bir arama algoritmasının nasıl yazılacağı gösterilmektedir.

Konu [iptali](cancellation-in-the-ppl.md) , paralel Desenler kitaplığındaki İptalin rolünü açıklar. Özel durum işlemenin kullanımı, paralel çalışmayı [eşzamanlılık:: task_group:: Cancel](reference/task-group-class.md#cancel) ve [concurrency:: structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) yöntemlerinin kullanımıyla iptal etmenin daha az verimli bir yoludur. Ancak, çalışmayı iptal etmek için özel durum işlemenin kullanılması uygun olan bir senaryo, görevleri veya paralel algoritmaları kullanan ancak iptal etmek için bir `task_group` veya `structured_task_group` nesnesi sağlamayan bir üçüncü taraf kitaplığına çağrı yaptığınızda gereklidir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir veri öğesi ve alt düğümlerin bir listesini içeren temel bir `tree` türünü gösterir. Aşağıdaki bölümde, her bir alt düğümde yinelemeli olarak bir iş işlevi gerçekleştiren `for_all` yönteminin gövdesi gösterilmektedir.

[!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnek, `for_all` yöntemini gösterir. Bu, ağaç içindeki her düğümde paralel olarak bir iş işlevi gerçekleştirmek için [eşzamanlılık::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasını kullanır.

[!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnek, belirtilen `tree` nesnesinde bir değer arayan `search_for_value` işlevini gösterir. Bu işlev, belirtilen değeri içeren bir ağaç düğümü bulduğunda oluşturduğu bir iş işlevine `for_all` metoduna geçer.

`tree` sınıfının bir üçüncü taraf kitaplığı tarafından sağlandığını ve bunu değiştiremeyeceğiniz varsayılır. Bu durumda, `for_all` yöntemi çağırana `task_group` veya `structured_task_group` nesnesi sağlamadığından özel durum işlemenin kullanımı uygundur. Bu nedenle, iş işlevi üst görev grubunu doğrudan iptal edemiyor.

Bir görev grubuna sağladığınız çalışma işlevi bir özel durum oluşturduğunda, çalışma zamanı görev grubundaki (herhangi bir alt görev grubu dahil) tüm görevleri durduruyor ve henüz başlatılmamış tüm görevleri atar. `search_for_value` işlevi, özel durumu yakalamak ve sonucu konsola yazdırmak için bir `try`-`catch` bloğu kullanır.

[!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnek bir `tree` nesnesi oluşturur ve paralel olarak birkaç değer arar. `build_tree` işlevi bu konunun ilerleyen kısımlarında gösterilmektedir.

[!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]

Bu örnek, paralel olarak değer aramak için [eşzamanlılık::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmasını kullanır. Bu algoritma hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="example"></a>Örnek

Aşağıdaki tamamlanmış örnek, temel bir ağaç yapısında değer aramak için özel durum işlemeyi kullanır.

[!code-cpp[concrt-task-tree-search#5](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_5.cpp)]

Bu örnek, aşağıdaki örnek çıktıyı üretir.

```Output
Found a node with value 32614.
Found a node with value 86131.
Did not find node with value 17522.
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `task-tree-search.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc Task-Tree-Search. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[task_group Sınıfı](reference/task-group-class.md)<br/>
[structured_task_group Sınıfı](../../parallel/concrt/reference/structured-task-group-class.md)<br/>
[parallel_for_each Işlevi](reference/concurrency-namespace-functions.md#parallel_for_each)
