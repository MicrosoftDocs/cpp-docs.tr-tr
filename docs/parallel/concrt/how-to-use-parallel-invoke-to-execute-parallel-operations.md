---
title: 'Nasıl yapılır: Paralel İşlemleri Yürütmek için parallel_invoke Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- parallel_invoke function, example
- calling multiple functions in parallel [Concurrency Runtime]
ms.assetid: a6aea69b-d647-4b7e-bf3b-e6a6a9880072
ms.openlocfilehash: 199b663331e3322601100206f222e80bbb7c8db0
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142263"
---
# <a name="how-to-use-parallel_invoke-to-execute-parallel-operations"></a>Nasıl yapılır: Paralel İşlemleri Yürütmek için parallel_invoke Kullanma

Bu örnek, paylaşılan bir veri kaynağı üzerinde birden çok işlem gerçekleştiren bir programın performansını artırmak için [eşzamanlılık::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmasının nasıl kullanılacağını gösterir. Kaynağı hiçbir işlem üzerinde değişiklik yaptığından, bu, basit bir şekilde paralel olarak Yürütülebilirler.

## <a name="example"></a>Örnek

`MyDataType`türünde bir değişken oluşturan aşağıdaki kod örneğini düşünün, bu değişkeni başlatmak için bir işlev çağırır ve sonra bu verilerde birden çok uzun işlem gerçekleştirir.

[!code-cpp[concrt-parallel-word-mining#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_1.cpp)]

`lengthy_operation1`, `lengthy_operation2`ve `lengthy_operation3` işlevleri `MyDataType` değişkenini değiştirmediğinden, bu işlevler ek değişiklikler yapılmadan paralel olarak çalıştırılabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, paralel olarak çalıştırmak için önceki örneği değiştirir. `parallel_invoke` algoritması her görevi paralel olarak yürütür ve tüm görevler tamamlandıktan sonra döndürür.

[!code-cpp[concrt-parallel-word-mining#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_2.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnek *,* Gutenberg.org ' den Homer tarafından bulunan ve bu dosya üzerinde birden çok işlem gerçekleştiren. Örnek öncelikle bu işlemleri işlem temelli olarak gerçekleştirir ve paralel olarak aynı işlemleri gerçekleştirir.

[!code-cpp[concrt-parallel-word-mining#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_3.cpp)]

Bu örnek, aşağıdaki örnek çıktıyı üretir.

```Output
Downloading 'The Iliad'...

Running serial version... took 953 ms.
Running parallel version... took 656 ms.

The most common words that have five or more letters are:
    their (953)
    shall (444)
    which (431)
    great (398)
    Hector (349)
    Achilles (309)
    through (301)
    these (268)
    chief (259)
The longest sequence of words that have the same first letter is:
    through the tempest to the tented
The following palindromes appear in the text:
    spots stops
    speed deeps
    keels sleek
```

Bu örnek, aynı veri kaynağı üzerinde işlem gören birden çok işlevi çağırmak için `parallel_invoke` algoritmasını kullanır. Yalnızca aynı verilerle ilgili olanları değil, herhangi bir işlev kümesini paralel olarak çağırmak için `parallel_invoke` algoritmasını kullanabilirsiniz.

`parallel_invoke` algoritması her çalışma işlevini paralel olarak çağırdığı için, performansı en uzun süreyi geçen (yani, çalışma zamanı ayrı bir işlemcide her bir işlevi işliyorsa) işlevi ile sınırlıdır. Bu örnek, kullanılabilir işlemci sayısından paralel olarak daha fazla görev gerçekleştiriyorsa, her işlemcide birden çok görev çalıştırılabilir. Bu durumda, performans, en uzun süre sonu alan görev grubu ile sınırlıdır.

Bu örnek paralel olarak üç görev gerçekleştirdiğinden, üçten fazla işlemciyi bulunan bilgisayarlarda ölçeği ölçeklendirmek için performansın beklenmemelidir. Performansı daha da geliştirmek için, en uzun çalışan görevleri daha küçük görevlere bölebilir ve bu görevleri paralel olarak çalıştırabilirsiniz.

İptal için desteğe ihtiyacınız yoksa [concurrency:: task_group](reference/task-group-class.md) ve [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) sınıfları yerine `parallel_invoke` algoritmasını kullanabilirsiniz. `parallel_invoke` algoritmanın görev grupları ile kullanımını karşılaştıran bir örnek için bkz. [nasıl yapılır: Parallel_invoke kullanarak paralel bir sıralama yordamı yazma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya `parallel-word-mining.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc/MD/DUNıCODE/D_AFXDLL Parallel-Word-Mining. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_invoke Işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)
