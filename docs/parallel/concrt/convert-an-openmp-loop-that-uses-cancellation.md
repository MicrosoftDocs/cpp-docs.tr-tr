---
title: 'Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için İptali Kullanan bir OpenMP Döngüsünü Dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, cancellation
- cancellation, converting from OpenMP to the Concurrency Runtime
ms.assetid: 4b0b3c33-bfa9-4e96-ae08-aef245a39cbb
ms.openlocfilehash: f4d4d8d1b2dbf60d0b4674229043c981d874292d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141830"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-cancellation-to-use-the-concurrency-runtime"></a>Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için İptali Kullanan bir OpenMP Döngüsünü Dönüştürme

Bazı paralel döngüler tüm yinelemelerin yürütülmesini gerektirmez. Örneğin, bir değer arayan bir algoritma, değer bulunduktan sonra sonlanacaktır. OpenMP, paralel bir döngüyü bölmek için bir mekanizma sağlamaz. Ancak, bir Boolean değeri veya bayrağını, çözümün bulunduğunu göstermek için bir döngü yinelemesi etkinleştirmek üzere kullanabilirsiniz. Eşzamanlılık Çalışma Zamanı, bir görevin henüz başlatılmamış diğer görevleri iptal etmesini sağlayan işlevler sağlar.

Bu örnekte, tüm yinelemelerin Eşzamanlılık Çalışma Zamanı iptal mekanizmasını kullanmak üzere çalışması için gerekli olmayan bir OpenMP [Parallel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[for](../../parallel/openmp/reference/for-openmp.md) döngüsünün nasıl dönüştürüleceği gösterilmektedir.

## <a name="example"></a>Örnek

Bu örnek, [std:: any_of](../../standard-library/algorithm-functions.md#any_of) algoritmasının paralel bir sürümünü uygulamak Için hem OpenMP hem de eşzamanlılık çalışma zamanı kullanır. Bu örneğin OpenMP sürümü, koşulun karşılandığından tüm paralel döngü yinelemeleri arasında koordine etmek için bir bayrak kullanır. Eşzamanlılık Çalışma Zamanı kullanan sürüm, koşul karşılandığında genel işlemi durdurmak için [concurrency:: structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) metodunu kullanır.

[!code-cpp[concrt-openmp#2](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-cancellation_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Using OpenMP...
9114046 is in the array.
Using the Concurrency Runtime...
9114046 is in the array.
```

, OpenMP kullanan sürümünde, işaret ayarlanmış olsa bile döngünün tüm yinelemeleri yürütülür. Ayrıca, bir görevin herhangi bir alt görevi varsa, iptal iletişim kurmak üzere bu alt görevler için de bayrağın kullanılabilir olması gerekir. Eşzamanlılık Çalışma Zamanı, bir görev grubu iptal edildiğinde, çalışma zamanı alt görevler de dahil olmak üzere tüm iş ağacını iptal eder. [Eşzamanlılık::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritması, işleri gerçekleştirmek için görevleri kullanır. Bu nedenle, döngünün bir yinelemesi kök görevi iptal ettiğinde, tüm hesaplama ağacı da iptal edilir. Bir iş ağacı iptal edildiğinde, çalışma zamanı yeni görevleri başlatmaz. Ancak çalışma zamanı, zaten başlatılmış olan görevlerin çalışmasına izin verir. Bu nedenle, `parallel_for_each` algoritması durumunda etkin döngü yinelemeleri kaynaklarını temizleyebilir.

Bu örneğin her iki sürümünde, dizi, arama yapılacak değerin birden fazla kopyasını içeriyorsa, birden çok döngü yinelemesi aynı anda sonucu ayarlayabilir ve genel işlemi iptal edebilir. Sorun, bir koşul karşılandığında yalnızca bir görevin iş gerçekleştirmesini gerektiriyorsa kritik bir bölüm gibi bir eşitleme temel alanı kullanabilirsiniz.

Ayrıca, PPL 'yi kullanan görevleri iptal etmek için özel durum işlemeyi da kullanabilirsiniz. İptal hakkında daha fazla bilgi için bkz. [PPL 'de iptal](cancellation-in-the-ppl.md).

`parallel_for_each` ve diğer paralel algoritmalar hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `concrt-omp-parallel-any-of.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc/OpenMP concrt-omp-Parallel-any-of. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)
