---
title: 'Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için İptali Kullanan bir OpenMP Döngüsünü Dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, cancellation
- cancellation, converting from OpenMP to the Concurrency Runtime
ms.assetid: 4b0b3c33-bfa9-4e96-ae08-aef245a39cbb
ms.openlocfilehash: f3a53113952a12b6b25839deb20548c56a9b7e1c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569578"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-cancellation-to-use-the-concurrency-runtime"></a>Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için İptali Kullanan bir OpenMP Döngüsünü Dönüştürme

Tüm yinelemeler yürütülüp bazı paralel döngüler gerek yoktur. Örneğin, değer bulunduktan sonra bir değeri arar bir algoritma sonlandırabilirsiniz. OpenMP paralel bir döngüden mekanizması sağlamaz. Ancak, çözüm bulundu göstermek için döngü yinelemesi etkinleştirmek için bir Boole değeri ya da bayrağını kullanabilirsiniz. Eşzamanlılık Çalışma zamanı henüz başlamamış diğer görevleri iptal etmek bir görev sağlayan işlevselliği sağlar.

Bu örnek bir OpenMP dönüştürülmesi gösterilmektedir [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[için](../../parallel/openmp/reference/for-openmp.md) döngü tüm yinelemeleri çalıştırmak eşzamanlılık çalışma zamanı iptal mekanizması kullanmak için gerekli değildir.

## <a name="example"></a>Örnek

Bu örnek bir paralel sürümünü uygulamak için OpenMP hem de eşzamanlılık çalışma zamanı kullanan [std::any_of](../../standard-library/algorithm-functions.md#any_of) algoritması. Bu örnekte OpenMP sürümü, koşulun karşılanması tüm paralel döngü yinelemesi arasında koordine etmek için bir bayrak kullanır. Eşzamanlılık Çalışma zamanı sürümünü kullanan [CONCURRENCY::structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) koşul karşılandığında genel işlemi durdurmak için yöntemi.

[!code-cpp[concrt-openmp#2](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-cancellation_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Using OpenMP...
9114046 is in the array.
Using the Concurrency Runtime...
9114046 is in the array.
```

OpenMP kullanan sürümünde, tüm döngü yinelemelerine yürütün, hatta bayrağı ayarlandığında. Bir görev alt görev için olsaydı, ayrıca, bayrağı da iptal iletişim kurmak için bu alt görevler tarafından kullanılabilmesini etmesi gerekir. Eşzamanlılık Çalışma zamanı içinde görev grubunu iptal edildiğinde, çalışma zamanı ağacının tümünü alt görevler de dahil olmak üzere iş iptal eder. [Concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritması, işi gerçekleştirmek için görevler kullanır. Bu nedenle, bir yineleme döngüsü kök görev iptal ettiğinde, hesaplama ağacının tümünü da iptal edildi. Bir iş ağacında iptal edildiğinde, çalışma zamanının yeni görevler başlamıyor. Ancak, çalışma zamanı tamamlanması zaten başlamış görevleri sağlar. Bu nedenle, durumunda, `parallel_for_each` algoritması, etkin döngü yinelemesi temiz kaynaklarını.

Bu örnekte her iki sürümünde de dizi değeri aramak için birden fazla kopyasını içeriyorsa döngü yinelemesi birden çok her aynı anda sonuç kümesi ve genel işlem iptal edebilirsiniz. Sorununuzu bir koşul karşılandığında iş, yalnızca bir görev gerçekleştiren gerektiriyorsa, bir eşitleme temel kritik bölümü gibi kullanabilirsiniz.

Özel durum işleme kullanan PPL görevleri iptal etmek için de kullanabilirsiniz. İptal işlemleri hakkında daha fazla bilgi için bkz. [ppl'de iptal](cancellation-in-the-ppl.md).

Hakkında daha fazla bilgi için `parallel_for_each` ve diğer paralel algoritmalar için bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `concrt-omp-parallel-any-of.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc/OpenMP concrt-omp-paralel-any-of.cpp**

## <a name="see-also"></a>Ayrıca Bkz.

[OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)

