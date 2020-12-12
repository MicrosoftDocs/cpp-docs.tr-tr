---
description: 'Daha fazla bilgi edinin: nasıl yapılır: bellek performansını artırmak için ayırma ve serbest kullanma'
title: 'Nasıl yapılır: Bellek Performansını Artırmak için Alloc ve Free Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- Alloc and Free, using [Concurrency Runtime]
- Using Alloc and Free [Concurrency Runtime]
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
ms.openlocfilehash: ab9a7bb9ad067bd7a5650b9e66d1708f08ffc183
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172576"
---
# <a name="how-to-use-alloc-and-free-to-improve-memory-performance"></a>Nasıl yapılır: Bellek Performansını Artırmak için Alloc ve Free Kullanma

Bu belgede, bellek performansını artırmak için [concurrency:: ayırma](reference/concurrency-namespace-functions.md#alloc) ve [concurrency:: Free](reference/concurrency-namespace-functions.md#free) işlevlerinin nasıl kullanılacağı gösterilmektedir. Her biri ve işleçlerini belirten üç farklı tür için, bir dizinin öğelerini paralel olarak ters çevirmek için gereken zamanı karşılaştırır `new` `delete` .

`Alloc`Ve `Free` işlevleri, birden çok iş parçacığı genellikle hem hem de ' i çağırdığınızda yararlı olur `Alloc` `Free` . Çalışma zamanı her iş parçacığı için ayrı bir bellek önbelleği barındırır; Bu nedenle, çalışma zamanı, kilitleri veya bellek engelleri kullanımı olmadan belleği yönetir.

## <a name="example-types-that-specify-new-and-delete-operators"></a>Örnek: New ve DELETE işleçlerini belirten türler

Aşağıdaki örnek, her birinin ve işleçlerini belirten üç tür `new` gösterir `delete` . `new_delete`Sınıfı Global `new` ve `delete` işleçlerini kullanır, `malloc_free` sınıfı C çalışma zamanı [malloc](../../c-runtime-library/reference/malloc.md) ve [Free](../../c-runtime-library/reference/free.md) işlevlerini kullanır ve `Alloc_Free` sınıf eşzamanlılık çalışma zamanı `Alloc` ve işlevleri kullanır `Free` .

[!code-cpp[concrt-allocators#1](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_1.cpp)]

## <a name="example-swap-and-reverse_array-functions"></a>Örnek: takas ve reverse_array işlevleri

Aşağıdaki örnekte `swap` ve `reverse_array` işlevleri gösterilmektedir. `swap`İşlevi, dizinin içeriğini belirtilen dizinlerle değiş tokuş eder. Geçici değişken için yığından bellek ayırır. `reverse_array`İşlevi büyük bir dizi oluşturur ve bu diziyi paralel olarak birkaç kez tersine çevirmek için gereken zamanı hesaplar.

[!code-cpp[concrt-allocators#2](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_2.cpp)]

## <a name="example-wmain-function"></a>Örnek: wmain işlevi

Aşağıdaki örnek, `wmain` `reverse_array` işlevinin `new_delete` `malloc_free` `Alloc_Free` her biri farklı bir bellek ayırma şeması kullanan,, ve türlerinde işlem yapması için gereken zamanı hesaplayan işlevi gösterir.

[!code-cpp[concrt-allocators#3](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_3.cpp)]

## <a name="complete-code-example"></a>Kod örneğini doldurun

Tüm örnek aşağıda verilmiştir.

[!code-cpp[concrt-allocators#4](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_4.cpp)]

Bu örnek, dört işlemcili bir bilgisayar için aşağıdaki örnek çıktıyı üretir.

```Output
Took 2031 ms with new/delete.
Took 1672 ms with malloc/free.
Took 656 ms with Alloc/Free.
```

Bu örnekte, ve işlevleri `Alloc` `Free` `Alloc` `Free` birden çok iş parçacığından genellikle bellek blokları ayırmak ve serbest bırakma için iyileştirildiğinden, ve işlevlerini kullanan tür en iyi bellek performansını sağlar.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `allocators.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc allocators. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Bellek yönetimi Işlevleri](../../parallel/concrt/memory-management-functions.md)<br/>
[Ayırma Işlevi](reference/concurrency-namespace-functions.md#alloc)<br/>
[Free Işlevi](reference/concurrency-namespace-functions.md#free)
