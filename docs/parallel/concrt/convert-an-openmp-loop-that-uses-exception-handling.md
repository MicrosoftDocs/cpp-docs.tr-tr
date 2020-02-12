---
title: 'Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için Özel Durum İşleme Kullanan bir OpenMP Döngüsünü Dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling, converting from OpenMP to the Concurrency Runtime
- converting from OpenMP to the Concurrency Runtime, exception handling
ms.assetid: 03c28196-21ba-439e-8641-afab1c283e1a
ms.openlocfilehash: 380a96eedb8a70965197c4a5ce0c5199bc268db5
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141808"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-exception-handling-to-use-the-concurrency-runtime"></a>Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için Özel Durum İşleme Kullanan bir OpenMP Döngüsünü Dönüştürme

Bu örnek, Eşzamanlılık Çalışma Zamanı özel durum işleme mekanizmasını kullanmak için özel durum işleme gerçekleştiren bir OpenMP [Parallel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[for](../../parallel/openmp/reference/for-openmp.md) döngüsünün nasıl dönüştürüleceğini gösterir.

OpenMP 'da, bir paralel bölgede oluşturulan bir özel durumun aynı iş parçacığı tarafından yakalanıp aynı bölgede işlenmesi gerekir. Paralel bölgeyi çıkar, varsayılan olarak işlemi sonlandıran işlenmemiş özel durum işleyicisi tarafından yakalanır.

Eşzamanlılık Çalışma Zamanı [eşzamanlılık:: task_group](reference/task-group-class.md) veya [eşzamanlılık:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesnesi gibi bir görev grubuna geçirdiğiniz bir çalışma işlevinin gövdesinde bir özel durum oluştururken veya [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for)gibi bir paralel algoritmada, çalışma zamanı bu özel durumu depolar ve görev grubunun veya algoritmanın bitmesini bekleyen bağlama göre sıraatar. Görev gruplarında, bekleyen bağlam [concurrency:: task_group:: wait](reference/task-group-class.md#wait), [concurrency:: structured_task_group:: wait](reference/structured-task-group-class.md#wait), concurrency:: [task_group:: run_and_wait](reference/task-group-class.md#run_and_wait)veya [concurrency:: structured_task_group:: run_and_wait](reference/structured-task-group-class.md#run_and_wait)çağıran bağlamdır. Bir paralel algoritma için, bekleyen bağlam, bu algoritmayı çağıran bağlamdır. Çalışma zamanı, alt görev grupları dahil olmak üzere görev grubundaki tüm etkin görevleri de durduruyor ve henüz başlatılmamış tüm görevleri atar.

## <a name="example"></a>Örnek

Bu örnek, bir OpenMP `parallel` bölgesindeki ve `parallel_for`çağrısındaki özel durumların nasıl işleneceğini gösterir. `do_work` işlevi, başarılı olmayan bir bellek ayırma isteği gerçekleştirir ve bu nedenle [std:: bad_alloc](../../standard-library/bad-alloc-class.md)türünde bir özel durum oluşturur. OpenMP kullanan sürümde, özel durumu oluşturan iş parçacığı de onu yakalamalı. Diğer bir deyişle, bir OpenMP paralel döngüsünün her yinelemesi özel durumu işlemelidir. Eşzamanlılık Çalışma Zamanı kullanan sürümde, ana iş parçacığı başka bir iş parçacığı tarafından oluşturulan bir özel durumu yakalar.

[!code-cpp[concrt-openmp#3](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-exception-handling_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Using OpenMP...
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
Using the Concurrency Runtime...
An error of type 'class std::bad_alloc' occurred.
```

Bu örneğin OpenMP kullanan sürümünde, özel durum ' de gerçekleşir ve her döngü yinelemesi tarafından işlenir. Eşzamanlılık Çalışma Zamanı kullanan sürümde, çalışma zamanı özel durumu depolar, tüm etkin görevleri sonlandırır, henüz başlamamış tüm görevleri atar ve özel durumu `parallel_for`çağıran bağlama göre sıralar.

Özel durum oluştuktan sonra OpenMP kullanan sürümün sonlandırılırsa, hatanın gerçekleştiği diğer döngü yinelemelerini işaret etmek için bir Boole bayrağı kullanabilirsiniz. Bu konudaki örnekte olduğu gibi, [Eşzamanlılık çalışma zamanı kullanmak Için Iptali kullanan bir OpenMP döngüsünü dönüştürme](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)bölümünde, bayrak ayarlandıysa sonraki döngü yinelemeleri hiçbir şey yapmaz. Buna karşılık, Eşzamanlılık Çalışma Zamanı kullanan döngünün özel durum oluştuktan sonra devam etmesini istiyorsanız, özel durumu paralel döngü gövdesinde işleyin.

Zaman uyumsuz aracılar ve hafif görevler gibi Eşzamanlılık Çalışma Zamanı diğer bileşenleri özel durumları taşımazlar. Bunun yerine, işlenmemiş özel durumlar işlenmemiş özel durum işleyicisi tarafından yakalanır ve bu işlem varsayılan olarak işlemi sonlandırır. Özel durum işleme hakkında daha fazla bilgi için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

`parallel_for` ve diğer paralel algoritmalar hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `concrt-omp-exceptions.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc/OpenMP concrt-omp-Exceptions. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)
