---
title: 'Nasıl yapılır: Bellek Performansını Artırmak için Alloc ve Free Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- Alloc and Free, using [Concurrency Runtime]
- Using Alloc and Free [Concurrency Runtime]
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
ms.openlocfilehash: d91734859cd7d3499979566f427c10a0f026941b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467827"
---
# <a name="how-to-use-alloc-and-free-to-improve-memory-performance"></a>Nasıl yapılır: Bellek Performansını Artırmak için Alloc ve Free Kullanma

Bu belgenin nasıl kullanıldığını gösterir [concurrency::Alloc](reference/concurrency-namespace-functions.md#alloc) ve [concurrency::Free](reference/concurrency-namespace-functions.md#free) bellek performansını artırmak için işlevleri. Üç farklı türleri için paralel bir dizinin öğeleri tersine çevirmek için gerekli zamanı karşılaştırır her belirtin `new` ve `delete` işleçleri.

`Alloc` Ve `Free` birden çok iş parçacığı hem de sık çağrı yaptığınızda işlevleri en kullanışlı `Alloc` ve `Free`. Çalışma zamanı, her iş parçacığı için ayrı bir önbellek tutar; Bu nedenle, bellek kilitleri ya da belleği engelleri kullanmadan çalışma zamanı yönetir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, her belirttiğiniz üç tür gösterir `new` ve `delete` işleçleri. `new_delete` Sınıfın kullandığı genel `new` ve `delete` işleçleri `malloc_free` sınıfın kullandığı C çalışma zamanı [malloc](../../c-runtime-library/reference/malloc.md) ve [ücretsiz](../../c-runtime-library/reference/free.md) işlevler ve `Alloc_Free` sınıf, eşzamanlılık çalışma zamanı kullanan `Alloc` ve `Free` işlevleri.

[!code-cpp[concrt-allocators#1](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_1.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği `swap` ve `reverse_array` işlevleri. `swap` İşlevi, belirtilen dizin konumundaki dizinin içeriğini birbiriyle değiştirir. Gelen öbek geçici değişken için bellek ayırır. `reverse_array` İşlevi büyük bir dizi oluşturur ve bu diziyi birkaç kez paralel olarak tersine çevirmek için gerekli süreyi ölçer.

[!code-cpp[concrt-allocators#2](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_2.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği `wmain` hesaplar için gerekli olan zamanı işlevi `reverse_array` gerçekleştirileceği işlevi `new_delete`, `malloc_free`, ve `Alloc_Free` türleri, her biri farklı bir bellek ayırma düzeni kullanır.

[!code-cpp[concrt-allocators#3](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_3.cpp)]

## <a name="example"></a>Örnek

Eksiksiz bir örnek aşağıda verilmiştir.

[!code-cpp[concrt-allocators#4](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_4.cpp)]

Bu örnekte, dört işlemciye sahip bir bilgisayar için aşağıdaki örnek çıktısı üretir.

```Output
Took 2031 ms with new/delete.
Took 1672 ms with malloc/free.
Took 656 ms with Alloc/Free.
```

Bu örnekte, bir tür kullanan `Alloc` ve `Free` işlevleri sağlayan en iyi bellek performansı nedeniyle `Alloc` ve `Free` işlevleri sık ayırarak ve birden çok bellek blokları serbest bırakma için iyileştirilmiştir iş parçacıkları.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `allocators.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc allocators.cpp**

## <a name="see-also"></a>Ayrıca Bkz.

[Bellek Yönetimi İşlevleri](../../parallel/concrt/memory-management-functions.md)<br/>
[Alloc işlevi](reference/concurrency-namespace-functions.md#alloc)<br/>
[Free işlevi](reference/concurrency-namespace-functions.md#free)

