---
title: 'Nasıl Yapılır: Eşzamanlılık Çalışma zamanı kullanmak için özel durum işleme kullanan bir OpenMP döngüsünü dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling, converting from OpenMP to the Concurrency Runtime
- converting from OpenMP to the Concurrency Runtime, exception handling
ms.assetid: 03c28196-21ba-439e-8641-afab1c283e1a
ms.openlocfilehash: 9fa5ff2bcdfa6680dde6e9316d143089bf586671
ms.sourcegitcommit: ee0103752884425843556a19cf418a504dc3cd02
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2018
ms.locfileid: "53738099"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-exception-handling-to-use-the-concurrency-runtime"></a>Nasıl Yapılır: Eşzamanlılık Çalışma zamanı kullanmak için özel durum işleme kullanan bir OpenMP döngüsünü dönüştürme

Bu örnek bir OpenMP dönüştürülmesi gösterilmektedir [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[için](../../parallel/openmp/reference/for-openmp.md) eşzamanlılık çalışma zamanı özel durum işleme mekanizmasını kullanmak için özel durum işleme gerçekleştiren bir döngü.

OpenMP içinde bir paralel bölgenin içinde oluşturulan bir özel durum yakalandı ve aynı bölgede aynı iş parçacığı tarafından işlenir. Varsayılan olarak işlemi sonlandıran yakalanamayan özel durum işleyicisi tarafından paralel bölgenin çıkışları bir özel durum yakalandı.

Eşzamanlılık gibi bir görev grubuna başarılı bir iş işlevin gövdesinde bir durum olduğunda çalışma zamanında, bir [concurrency::task_group](reference/task-group-class.md) veya [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesnesi veya gibi paralel algoritma için [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for), çalışma zamanı bu özel durum depolar ve görev grubu veya algoritması tamamlanması için bekleyeceği bağlam sürekliliğe devreder. Görev grupları için çağıran bağlamını bekleme bağlamıdır [CONCURRENCY::task_group:: wait](reference/task-group-class.md#wait), [CONCURRENCY::structured_task_group](reference/structured-task-group-class.md#wait), [concurrency::task_group::run_and _wait](reference/task-group-class.md#run_and_wait), veya [CONCURRENCY::structured_task_group:: run_and_wait](reference/structured-task-group-class.md#run_and_wait). Bir paralel algoritma için bu algoritmayı adlı bağlam bekleme bağlamdır. Çalışma zamanı ayrıca alt görev grupları de dahil olmak üzere görev grubunda olan tüm etkin görevleri durdurur ve henüz başlamamış herhangi bir görevi atar.

## <a name="example"></a>Örnek

Bu örnek, bir OpenMP özel durumların nasıl işleneceğini gösterir. `parallel` bölge ve çağrıda `parallel_for`. `do_work` İşlevi başarılı olmaz ve bu nedenle türünde bir özel durum oluşturur, bir bellek ayırma isteği gerçekleştirir [std::bad_alloc](../../standard-library/bad-alloc-class.md). OpenMP kullanan sürümünde özel durum oluşturan iş parçacığı da bunu yakalayıp yakalamayacağınıza gerekir. Diğer bir deyişle, her bir yinelemesini paralel bir OpenMP döngüsünü özel durum işlemesi gerekir. Eşzamanlılık Çalışma zamanı kullanan sürümünde başka bir iş parçacığı tarafından oluşturulan bir özel durum ana iş parçacığı yakalar.

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

OpenMP kullanan bu örnek sürümünde, özel durum oluşur ve her döngü yinelemesinin tarafından gerçekleştirilir. Eşzamanlılık Çalışma zamanı sürümünde, çalışma zamanı özel depolar, tüm etkin görevleri durdurur, yok henüz kullanmaya herhangi bir görevi atar ve özel durumu çağıran bağlamını sürekliliğe devreder `parallel_for`.

Özel durum oluştuktan sonra OpenMP kullanan sürüm sonlandırır gerekiyorsa, diğer döngü yinelemesi için hata oluştuğunu belirten bir Boole bayrağı kullanabilirsiniz. Bu konudaki örnekte olduğu gibi [nasıl yapılır: Bu kullanan eşzamanlılık çalışma zamanı kullanmak için İptali bir OpenMP döngüsünü dönüştürme](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md), sonraki döngü yinelemesi yaptığınız şey bayrağı ayarlandıysa. Özel durum oluştuktan sonra eşzamanlılık çalışma zamanı kullanan döngü devam etmesini gerektiriyorsa, buna karşılık, paralel döngü gövdesi içinde özel durumu işle.

Eşzamanlılık Çalışma zamanı zaman uyumsuz aracılar ve Basit görevler gibi diğer bileşenlerden özel durumları taşıma değil. Bunun yerine, varsayılan olarak işlemi sonlandıran yakalanamayan özel durum işleyici tarafından işlenmeyen özel durumları yakalanır. Özel durum işleme hakkında daha fazla bilgi için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

Hakkında daha fazla bilgi için `parallel_for` ve diğer paralel algoritmalar için bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `concrt-omp-exceptions.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc/OpenMP concrt-omp-exceptions.cpp**

## <a name="see-also"></a>Ayrıca Bkz.

[OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)

