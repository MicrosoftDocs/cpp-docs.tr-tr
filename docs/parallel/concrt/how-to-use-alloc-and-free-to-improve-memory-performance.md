---
title: 'Nasıl yapılır: Bellek Performansını Artırmak için Alloc ve Free Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- Alloc and Free, using [Concurrency Runtime]
- Using Alloc and Free [Concurrency Runtime]
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
ms.openlocfilehash: 8438e833262d42c6083f48f759501c573a35c772
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142781"
---
# <a name="how-to-use-alloc-and-free-to-improve-memory-performance"></a>Nasıl yapılır: Bellek Performansını Artırmak için Alloc ve Free Kullanma

Bu belgede, bellek performansını artırmak için [concurrency:: ayırma](reference/concurrency-namespace-functions.md#alloc) ve [concurrency:: Free](reference/concurrency-namespace-functions.md#free) işlevlerinin nasıl kullanılacağı gösterilmektedir. Her biri `new` ve `delete` işleçlerini belirten üç farklı tür için, bir dizinin öğelerini paralel olarak ters çevirmek için gereken zamanı karşılaştırır.

`Alloc` ve `Free` işlevleri, birden çok iş parçacığı genellikle hem `Alloc` hem de `Free`çağırdığınızda en yararlı seçenektir. Çalışma zamanı her iş parçacığı için ayrı bir bellek önbelleği barındırır; Bu nedenle, çalışma zamanı, kilitleri veya bellek engelleri kullanımı olmadan belleği yönetir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, her biri `new` ve `delete` işleçlerini belirten üç tür gösterir. `new_delete` sınıfı, genel `new` ve `delete` işleçlerini kullanır, `malloc_free` sınıfı C çalışma zamanı [malloc](../../c-runtime-library/reference/malloc.md) ve [Free](../../c-runtime-library/reference/free.md) işlevlerini kullanır ve `Alloc_Free` sınıfı eşzamanlılık çalışma zamanı `Alloc` ve `Free` işlevlerini kullanır.

[!code-cpp[concrt-allocators#1](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_1.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnekte `swap` ve `reverse_array` işlevleri gösterilmektedir. `swap` işlevi, dizinin içeriğini belirtilen indeksler. Geçici değişken için yığından bellek ayırır. `reverse_array` işlevi büyük bir dizi oluşturur ve bu diziyi paralel olarak birkaç kez tersine çevirmek için gereken zamanı hesaplar.

[!code-cpp[concrt-allocators#2](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_2.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnek, her biri farklı bir bellek ayırma şeması kullanan `new_delete`, `malloc_free`ve `Alloc_Free` türlerinde işlem yapması için `reverse_array` gerekli zamanı hesaplayan `wmain` işlevini gösterir.

[!code-cpp[concrt-allocators#3](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_3.cpp)]

## <a name="example"></a>Örnek

Tüm örnek aşağıda verilmiştir.

[!code-cpp[concrt-allocators#4](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_4.cpp)]

Bu örnek, dört işlemcili bir bilgisayar için aşağıdaki örnek çıktıyı üretir.

```Output
Took 2031 ms with new/delete.
Took 1672 ms with malloc/free.
Took 656 ms with Alloc/Free.
```

Bu örnekte, `Alloc` ve `Free` işlevlerini kullanan tür, `Alloc` ve `Free` işlevleri birden çok iş parçacığından genellikle bellek blokları ayırmak ve serbest bırakma için iyileştirildiğinden, en iyi bellek performansını sağlar.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `allocators.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc allocators. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Yönetimi İşlevleri](../../parallel/concrt/memory-management-functions.md)<br/>
[Ayırma Işlevi](reference/concurrency-namespace-functions.md#alloc)<br/>
[Free Işlevi](reference/concurrency-namespace-functions.md#free)
