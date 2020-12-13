---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: paralel Işlemleri yürütmek için parallel_invoke kullanma'
title: 'Nasıl yapılır: Paralel İşlemleri Yürütmek için parallel_invoke Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- parallel_invoke function, example
- calling multiple functions in parallel [Concurrency Runtime]
ms.assetid: a6aea69b-d647-4b7e-bf3b-e6a6a9880072
ms.openlocfilehash: e31cc19a1670cf7ccf9d664ffbed33fea98134a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334661"
---
# <a name="how-to-use-parallel_invoke-to-execute-parallel-operations"></a>Nasıl yapılır: Paralel İşlemleri Yürütmek için parallel_invoke Kullanma

Bu örnek, paylaşılan bir veri kaynağı üzerinde birden çok işlem gerçekleştiren bir programın performansını artırmak için [eşzamanlılık::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmasının nasıl kullanılacağını gösterir. Kaynağı hiçbir işlem üzerinde değişiklik yaptığından, bu, basit bir şekilde paralel olarak Yürütülebilirler.

## <a name="example-create-initialize-and-perform-operations-on-a-variable"></a>Örnek: bir değişkende işlem oluşturma, başlatma ve gerçekleştirme

Türünde bir değişken oluşturan `MyDataType` , bu değişkeni başlatmak için bir işlev çağıran ve ardından bu verilerde birden çok uzun işlem gerçekleştiren aşağıdaki kod örneğini göz önünde bulundurun.

[!code-cpp[concrt-parallel-word-mining#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_1.cpp)]

`lengthy_operation1`, `lengthy_operation2` , Ve `lengthy_operation3` işlevleri değişkeni değiştirmediğinden, `MyDataType` Bu işlevler ek değişiklik yapılmadan paralel olarak çalıştırılabilir.

## <a name="example-run-previous-example-in-parallel"></a>Örnek: önceki örneği paralel olarak çalıştır

Aşağıdaki örnek, paralel olarak çalıştırmak için önceki örneği değiştirir. `parallel_invoke`Algoritma her görevi paralel olarak yürütür ve tüm görevler tamamlandıktan sonra döndürür.

[!code-cpp[concrt-parallel-word-mining#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_2.cpp)]

## <a name="example-perform-multiple-operations-on-a-downloaded-file"></a>Örnek: indirilen bir dosyada birden çok işlem gerçekleştirin

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

Bu örnek `parallel_invoke` , aynı veri kaynağı üzerinde işlem gören birden çok işlevi çağırmak için algoritmasını kullanır. `parallel_invoke`Yalnızca aynı verilere yönelik olanları değil, herhangi bir işlev kümesini paralel olarak çağırmak için algoritmayı kullanabilirsiniz.

`parallel_invoke`Algoritma her çalışma işlevini paralel olarak çağırdığı için, performansı en uzun süreyi geçen (yani, çalışma zamanı ayrı bir işlemcide her işlevi işliyorsa) işlevi ile sınırlıdır. Bu örnek, kullanılabilir işlemci sayısından paralel olarak daha fazla görev gerçekleştiriyorsa, her işlemcide birden çok görev çalıştırılabilir. Bu durumda, performans, en uzun süre sonu alan görev grubu ile sınırlıdır.

Bu örnek paralel olarak üç görev gerçekleştirdiğinden, üçten fazla işlemciyi bulunan bilgisayarlarda ölçeği ölçeklendirmek için performansın beklenmemelidir. Performansı daha da geliştirmek için, en uzun çalışan görevleri daha küçük görevlere bölebilir ve bu görevleri paralel olarak çalıştırabilirsiniz.

`parallel_invoke`İptal için desteğe ihtiyacınız yoksa [concurrency:: task_group](reference/task-group-class.md) ve [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) sınıfları yerine algoritmayı kullanabilirsiniz. Algoritma kullanımını görev grupları ile karşılaştıran bir örnek için `parallel_invoke` bkz. [nasıl yapılır: kullanımı Parallel_invoke, paralel bir sıralama yordamı yazmak için](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `parallel-word-mining.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc/MD/DUNıCODE/D_AFXDLL Parallel-Word-Mining. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_invoke Işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)
