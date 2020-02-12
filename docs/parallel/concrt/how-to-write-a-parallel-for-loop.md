---
title: 'Nasıl yapılır: parallel_for Döngüsü Yazma'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel_for loop [Concurrency Runtime]
- parallel_for function, example
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
ms.openlocfilehash: 5903114a12de46dc06929c83e9995b39d0136810
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141867"
---
# <a name="how-to-write-a-parallel_for-loop"></a>Nasıl yapılır: parallel_for Döngüsü Yazma

Bu örnek, iki matrisinin çarpımını hesaplamak için [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) nasıl kullanacağınızı gösterir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, iki kare matrisinin çarpımını hesaplayan `matrix_multiply` işlevi gösterilmektedir.

[!code-cpp[concrt-parallel-matrix-multiply#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_1.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnekte, dış döngüyü paralel olarak gerçekleştirmek için `parallel_for` algoritmasını kullanan `parallel_matrix_multiply` işlevi gösterilmektedir.

[!code-cpp[concrt-parallel-matrix-multiply#2](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_2.cpp)]

Bu örnek, yalnızca paralel işleme yükünden faydalanmak için yeterli iş gerçekleştirdiğinden, dış döngüyü paralelleştirme. İç döngüyü paralel hale getirmek düşünüyorsanız, iç döngünün gerçekleştirdiği küçük iş miktarı paralel işleme yükünü aşmadığı için performans artışı elde edersiniz. Bu nedenle, dış döngüyü paralelleştirme, çoğu sistemde eşzamanlılık avantajlarından en iyi şekilde yararlanmanın en iyi yoludur.

## <a name="example"></a>Örnek

Aşağıdaki daha kapsamlı örnek, `matrix_multiply` işlevinin performansını `parallel_matrix_multiply` işlevi ile karşılaştırır.

[!code-cpp[concrt-parallel-matrix-multiply#3](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_3.cpp)]

Aşağıdaki örnek çıktı, dört işlemcili bir bilgisayar içindir.

```Output
serial: 3853
parallel: 1311
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya `parallel-matrix-multiply.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc Parallel-Matrix-Multiply. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_for Işlevi](reference/concurrency-namespace-functions.md#parallel_for)
