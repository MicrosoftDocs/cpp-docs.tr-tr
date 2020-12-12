---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: parallel_for döngüsü yazma'
title: 'Nasıl yapılır: parallel_for Döngüsü Yazma'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel_for loop [Concurrency Runtime]
- parallel_for function, example
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
ms.openlocfilehash: ccf66c3e457b540721f0a76722b9d17206cf0f7f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205700"
---
# <a name="how-to-write-a-parallel_for-loop"></a>Nasıl yapılır: parallel_for Döngüsü Yazma

Bu örnek, iki matrisinin çarpımını hesaplamak için [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) nasıl kullanacağınızı gösterir.

## <a name="example-compute-the-product-of-two-matrices"></a>Örnek: iki matrisin çarpımını hesaplama

Aşağıdaki örnek, `matrix_multiply` iki kare matrisinin çarpımını hesaplayan işlevi gösterir.

[!code-cpp[concrt-parallel-matrix-multiply#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_1.cpp)]

## <a name="example-compute-a-matrix-multiply-in-parallel"></a>Örnek: bir matris çarpini paralel olarak hesaplama

Aşağıdaki örnek, `parallel_matrix_multiply` `parallel_for` dış döngüyü paralel olarak gerçekleştirmek için algoritmayı kullanan işlevini gösterir.

[!code-cpp[concrt-parallel-matrix-multiply#2](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_2.cpp)]

Bu örnek, yalnızca paralel işleme yükünden faydalanmak için yeterli iş gerçekleştirdiğinden, dış döngüyü paralelleştirme. İç döngüyü paralel hale getirmek düşünüyorsanız, iç döngünün gerçekleştirdiği küçük iş miktarı paralel işleme yükünü aşmadığı için performans artışı elde edersiniz. Bu nedenle, dış döngüyü paralelleştirme, çoğu sistemde eşzamanlılık avantajlarından en iyi şekilde yararlanmanın en iyi yoludur.

## <a name="example-finished-parallel_for-loop-code-sample"></a>Örnek: parallel_for döngü kodu örneği tamamlandı

Aşağıdaki daha fazla örnek, işlevi ile işlevin performansını karşılaştırır `matrix_multiply` `parallel_matrix_multiply` .

[!code-cpp[concrt-parallel-matrix-multiply#3](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_3.cpp)]

Aşağıdaki örnek çıktı, dört işlemcili bir bilgisayar içindir.

```Output
serial: 3853
parallel: 1311
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `parallel-matrix-multiply.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Parallel-Matrix-Multiply. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_for Işlevi](reference/concurrency-namespace-functions.md#parallel_for)
