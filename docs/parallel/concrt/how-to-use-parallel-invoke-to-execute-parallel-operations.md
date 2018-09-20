---
title: 'Nasıl yapılır: paralel işlemleri yürütmek için parallel_invoke kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parallel_invoke function, example
- calling multiple functions in parallel [Concurrency Runtime]
ms.assetid: a6aea69b-d647-4b7e-bf3b-e6a6a9880072
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44d17bd45966c54a8a6c79afb0168a9407dd3e24
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374006"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>Nasıl yapılır: Paralel İşlemleri Yürütmek için parallel_invoke Kullanma

Bu örnek nasıl kullanılacağını gösterir [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) bir paylaşılan veri kaynağı üzerinde birden çok işlem gerçekleştiren bir programın performansını artırmak için kullanılan algoritma. Bir işlem kaynağını değiştirmek için bunlar basit bir şekilde paralel olarak gerçekleştirilebilir.

## <a name="example"></a>Örnek

Türünde bir değişken oluşturan aşağıdaki kod örneği göz önünde bulundurun `MyDataType`, bu değişkeni başlatmak için bir işlev çağırır ve ardından bu verileri birden çok uzun işlemleri gerçekleştirir.

[!code-cpp[concrt-parallel-word-mining#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_1.cpp)]

Varsa `lengthy_operation1`, `lengthy_operation2`, ve `lengthy_operation3` işlevleri değiştirmeyin `MyDataType` değişken, bu işlevler paralel ek değişiklikler olmadan yürütülebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, paralel olarak çalıştırmak için önceki örnekte değiştirir. `parallel_invoke` Algoritması her görevi paralel olarak yürütür ve tüm görevler tamamlandıktan sonra döndürür.

[!code-cpp[concrt-parallel-word-mining#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_2.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnek indirir *Iliad* tarafından Homer gutenberg.org gelen ve bu dosyayı birden çok işlem gerçekleştirir. Örnek, ilk olarak bu işlemlerin seri olarak gerçekleştirir ve ardından işlemlerin aynısını, paralel olarak gerçekleştirir.

[!code-cpp[concrt-parallel-word-mining#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_3.cpp)]

Bu örnek, aşağıdaki örnek çıktısı üretir.

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

Bu örnekte `parallel_invoke` birden çok çağırmak için algoritma işlevleri davranan aynı veri kaynağı. Kullanabileceğiniz `parallel_invoke` paralel olarak aynı veri üzerinde oynama yapmak olanlar değil yalnızca herhangi bir kümesi işlevleri çağırmak için kullanılan algoritma.

Çünkü `parallel_invoke` algoritmasını paralel olarak her iş işlevi çağırır, kendi performans (diğer bir deyişle, çalışma zamanı her işlevin ayrı bir işlemcide işlerse) tamamlanması uzun zaman alan işlev sınırlıdır. Bu örnek, paralel kullanılabilir işlemci sayısından daha fazla görevleri gerçekleştiriyorsa, birden çok görev her işlemci üzerinde çalıştırabilirsiniz. Bu durumda, performans, tamamlanması uzun zaman alan görev grubu tarafından sınırlıdır.

Bu örnekte üç görevleri paralel olarak gerçekleştirir. çünkü üçten fazla işlemcilere sahip bilgisayarlarda ölçeklendirmek için performans beklememeniz gerekir. Daha fazla performansı artırmak için uzun soluklu görevlerin daha küçük görevlere bölün ve bu görevler paralel olarak çalışır.

Kullanabileceğiniz `parallel_invoke` algoritması yerine [concurrency::task_group](reference/task-group-class.md) ve [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) iptal için destek gerekmiyorsa sınıfları. Kullanımını karşılaştıran bir örnek `parallel_invoke` görev grupları ve algoritma bkz [nasıl yapılır: paralel sıralama rutini yazmak için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `parallel-word-mining.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc/MD/DUNICODE /D_AFXDLL paralel word mining.cpp**

## <a name="see-also"></a>Ayrıca Bkz.

[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_invoke işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)

