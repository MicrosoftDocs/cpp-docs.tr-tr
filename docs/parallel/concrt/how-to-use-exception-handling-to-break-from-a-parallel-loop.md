---
description: 'Daha fazla bilgi edinin: nasıl yapılır: paralel bir döngüden ayırmak için özel durum Işlemeyi kullanma'
title: 'Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için Özel Durum İşlemeyi Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- search algorithm, writing [Concurrency Runtime]
- writing a search algorithm [Concurrency Runtime]
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
ms.openlocfilehash: aedad8f5851a606b91894ea07fce7e666d307992
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334684"
---
# <a name="how-to-use-exception-handling-to-break-from-a-parallel-loop"></a>Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için Özel Durum İşlemeyi Kullanma

Bu konu başlığı altında, temel ağaç yapısına yönelik bir arama algoritmasının nasıl yazılacağı gösterilmektedir.

Konu [iptali](cancellation-in-the-ppl.md) , paralel Desenler kitaplığındaki İptalin rolünü açıklar. Özel durum işlemenin kullanımı, paralel çalışmayı [eşzamanlılık:: task_group:: Cancel](reference/task-group-class.md#cancel) ve [concurrency:: structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) yöntemlerinin kullanımıyla iptal etmenin daha az verimli bir yoludur. Bununla birlikte, çalışmayı iptal etmek için özel durum işlemenin kullanılması uygun olan bir senaryo, görevler veya paralel algoritmalar kullanan ancak `task_group` iptal etmek için bir veya nesnesi sağlamayan bir üçüncü taraf kitaplığına çağrı yaptığınızda yapılır `structured_task_group` .

## <a name="example-basic-tree-type"></a>Örnek: temel ağaç türü

Aşağıdaki örnek, `tree` bir veri öğesi ve alt düğümlerin bir listesini içeren temel bir türü gösterir. Aşağıdaki bölümde `for_all` , her bir alt düğümde yinelemeli olarak bir iş işlevi gerçekleştiren yönteminin gövdesi gösterilmektedir.

[!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]

## <a name="example-perform-work-in-parallel"></a>Örnek: işi paralel olarak gerçekleştirme

Aşağıdaki örnekte `for_all` yöntemi gösterilmektedir. Bu, ağaç içindeki her düğümde paralel olarak bir iş işlevi gerçekleştirmek için [eşzamanlılık::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasını kullanır.

[!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]

## <a name="example--search-the-tree-for-a-value"></a>Örnek: ağaçta bir değer arayın

Aşağıdaki örnek, `search_for_value` belirtilen nesnede bir değer arayan işlevini gösterir `tree` . Bu işlev, `for_all` belirtilen değeri içeren bir ağaç düğümü bulduğunda oluşturan çalışma işlevine yöntemine geçer.

`tree`Sınıfın bir üçüncü taraf kitaplığı tarafından sağlandığını ve bunu değiştiremeyeceğiniz varsayın. Bu durumda, `for_all` Yöntem `task_group` çağıran için bir veya nesnesi sağlamadığı için özel durum işlemenin kullanılması uygundur `structured_task_group` . Bu nedenle, iş işlevi üst görev grubunu doğrudan iptal edemiyor.

Bir görev grubuna sağladığınız çalışma işlevi bir özel durum oluşturduğunda, çalışma zamanı görev grubundaki (herhangi bir alt görev grubu dahil) tüm görevleri durduruyor ve henüz başlatılmamış tüm görevleri atar. `search_for_value`İşlevi **`try`** - **`catch`** özel durumu yakalamak ve sonucu konsola yazdırmak için bir blok kullanır.

[!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]

## <a name="example-create-and-search-a-tree-in-parallel"></a>Örnek: bir ağacı paralel olarak oluşturma ve arama

Aşağıdaki örnek bir nesnesi oluşturur `tree` ve paralel olarak birkaç değer arar. `build_tree`İşlev bu konunun ilerleyen kısımlarında gösterilmektedir.

[!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]

Bu örnek, paralel olarak değer aramak için [eşzamanlılık::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmasını kullanır. Bu algoritma hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="example-finished-exception-handling-code-sample"></a>Örnek: özel durum işleme kod örneği tamamlandı

Aşağıdaki tamamlanmış örnek, temel bir ağaç yapısında değer aramak için özel durum işlemeyi kullanır.

[!code-cpp[concrt-task-tree-search#5](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_5.cpp)]

Bu örnek, aşağıdaki örnek çıktıyı üretir.

```Output
Found a node with value 32614.
Found a node with value 86131.
Did not find node with value 17522.
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `task-tree-search.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Task-Tree-Search. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[task_group sınıfı](reference/task-group-class.md)<br/>
[structured_task_group sınıfı](../../parallel/concrt/reference/structured-task-group-class.md)<br/>
[parallel_for_each Işlevi](reference/concurrency-namespace-functions.md#parallel_for_each)
