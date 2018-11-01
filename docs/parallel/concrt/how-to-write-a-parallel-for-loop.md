---
title: 'Nasıl yapılır: parallel_for Döngüsü Yazma'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel_for loop [Concurrency Runtime]
- parallel_for function, example
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
ms.openlocfilehash: 5caba385304e97bf2e1008a44724c792d56124f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592727"
---
# <a name="how-to-write-a-parallelfor-loop"></a>Nasıl yapılır: parallel_for Döngüsü Yazma

Bu örnek nasıl kullanılacağını gösterir [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) iki matrislerde çarpımını için.

## <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği `matrix_multiply` işlevin iki kare matrisler çarpımını hesaplar.

[!code-cpp[concrt-parallel-matrix-multiply#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_1.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği `parallel_matrix_multiply` kullanan işlevi `parallel_for` dış döngü paralel olarak gerçekleştirmenin algoritması.

[!code-cpp[concrt-parallel-matrix-multiply#2](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_2.cpp)]

Bu örnekte, yalnızca yeterli iş yükü paralel işleme için yararlanmasını gerçekleştirdiğinden dış döngü parallelizes. İç döngü paralel hale getirmek, iç döngü gerçekleştiren iş az miktarda ek yükü paralel işleme için üstesinden değildir çünkü, kazanç performansını almazsınız. Bu nedenle, dış döngü paralelleştirmek yalnızca çoğu sistemde yararlarını en üst düzeye çıkarmak için en iyi yoludur.

## <a name="example"></a>Örnek

Aşağıdaki daha eksiksiz bir örnek performansını karşılaştırır `matrix_multiply` karşı işlev `parallel_matrix_multiply` işlevi.

[!code-cpp[concrt-parallel-matrix-multiply#3](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_3.cpp)]

Aşağıdaki örnek çıktıda dört işlemciye sahip bir bilgisayar içindir.

```Output
serial: 3853
parallel: 1311
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `parallel-matrix-multiply.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc paralel-matris-multiply.cpp**

## <a name="see-also"></a>Ayrıca Bkz.

[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_for işlevi](reference/concurrency-namespace-functions.md#parallel_for)

