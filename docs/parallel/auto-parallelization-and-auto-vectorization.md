---
title: Otomatik Paralelleştirme ve Otomatik Vektörleştirme
ms.date: 11/04/2016
ms.assetid: ec71583a-287b-4599-8767-1d255e080fe3
ms.openlocfilehash: adc0dd9346cc2850b02e01804e26044c367f2d14
ms.sourcegitcommit: fcc3aeb271449f8be80348740cffef39ba543407
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/29/2020
ms.locfileid: "82538623"
---
# <a name="auto-parallelization-and-auto-vectorization"></a>Otomatik Paralelleştirme ve Otomatik Vektörleştirme

Otomatik paralelleştirme ve otomatik Vektörleştirici, kodunuzdaki döngüler için otomatik performans kazancı sağlamak üzere tasarlanmıştır.

## <a name="auto-parallelizer"></a>Otomatik paralelleştirme

[/Qpar](../build/reference/qpar-auto-parallelizer.md) derleyici anahtarı, kodunuzdaki döngülerin *Otomatik paralelleştirilmesini* mümkün hale getirme imkanı sunar. Mevcut kodunuzu değiştirmeden bu bayrağı belirttiğinizde derleyici, paralelleştirme avantajlarından faydalanabilecek döngüleri bulmak için kodu değerlendirir. Çok daha fazla çalışmadığı ve bu nedenle paralel hale getirme işleminin bir iş parçacığı havuzu, ekstra eşitleme veya başka bir işlem tarafından yararlanmak yerine performansı hafiflemediği için, derleyici, paralelleştirme döngülerinin seçilmesinde bir koruyucu olur. Örneğin, döngünün üst sınırının derleme zamanında bilinmediğini belirten aşağıdaki örneği göz önünde bulundurun:

```cpp
void loop_test(int u) {
   for (int i=0; i<u; ++i)
      A[i] = B[i] * C[i];
}
```

`u` Küçük bir değer olabileceğinden, derleyici bu döngüyü otomatik olarak paralel hale getirmek. Ancak, her zaman büyük olacağını bildiğiniz `u` için yine de paralelleştirmeye devam edebilirsiniz. Otomatik paralelleştirme özelliğini etkinleştirmek için [#pragma loop (hint_parallel (n))](../preprocessor/loop.md)belirtin; burada `n` , paralel hale getirmek arası iş parçacığı sayısıdır. Aşağıdaki örnekte, derleyici bu döngüyü 8 iş parçacığı boyunca paralel hale getirmek dener.

```cpp
void loop_test(int u) {
#pragma loop(hint_parallel(8))
   for (int i=0; i<u; ++i)
      A[i] = B[i] * C[i];
}
```

Tüm [pragma yönergelerinde](../preprocessor/pragma-directives-and-the-pragma-keyword.md)olduğu gibi, alternatif pragma sözdizimi `__pragma(loop(hint_parallel(n)))` de desteklenir.

Derleyicinin paralel hale getirmek izin vermese de bazı döngüler vardır. Bir örneği aşağıda verilmiştir:

```cpp
#pragma loop(hint_parallel(8))
for (int i=0; i<upper_bound(); ++i)
    A[i] = B[i] * C[i];
```

İşlev `upper_bound()` her çağrıldığında değişebilir. Üst sınır tanınamadığı için, derleyici bu döngüyü neden paralel hale getirmek, bunu açıklayan bir tanılama iletisi yayabilir. Aşağıdaki örnek, paralelleştirilmiş bir döngü, paralelleştirilmedi bir döngü, komut isteminde kullanılacak derleyici söz dizimini ve her komut satırı seçeneği için derleyici çıktısını gösterir:

```cpp
int A[1000];
void test() {
#pragma loop(hint_parallel(0))
    for (int i=0; i<1000; ++i) {
        A[i] = A[i] + 1;
    }

    for (int i=1000; i<2000; ++i) {
        A[i] = A[i] + 1;
    }
}
```

Şu komutu kullanarak derleniyor:

`cl d:\myproject\mylooptest.cpp /O2 /Qpar /Qpar-report:1`

Bu çıktıyı verir:

```Output
--- Analyzing function: void __cdecl test(void)
d:\myproject\mytest.cpp(4) : loop parallelized
```

Şu komutu kullanarak derleniyor:

`cl d:\myproject\mylooptest.cpp /O2 /Qpar /Qpar-report:2`

Bu çıktıyı verir:

```Output
--- Analyzing function: void __cdecl test(void)
d:\myproject\mytest.cpp(4) : loop parallelized
d:\myproject\mytest.cpp(4) : loop not parallelized due to reason '1008'
```

İki farklı [/Qpar-report (otomatik paralelleştirme raporlama düzeyi)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md) seçenekleri arasındaki çıkışdaki farka dikkat edin. `/Qpar-report:1`paralelleştirme iletilerini yalnızca başarıyla paralelleştirilmiş döngüler için verir. `/Qpar-report:2`hem başarılı hem de başarısız döngü paralelleştirmesinde paralelleştirme iletileri verir.

Neden kodları ve iletileri hakkında daha fazla bilgi için bkz. [Vektörtorizer ve paralelleştirme iletileri](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).

## <a name="auto-vectorizer"></a>Otomatik Vektörleştirici

Otomatik Vektörleştirici, kodunuzdaki döngüleri analiz eder ve mümkünse hedef bilgisayardaki vektör yazmaçlarını ve yönergeleri kullanır. Bu, kodunuzun performansını iyileştirebilir. Derleyici, Intel veya AMD işlemcilerde SSE2, AVX ve AVX2 yönergelerini veya [/Arch](../build/reference/arch-minimum-cpu-architecture.md) ANAHTARıNA göre ARM işlemcileriyle ilgili Neon yönergelerini hedefler.

Otomatik Vektörleştirici, `/arch` anahtar tarafından belirtilenden farklı yönergeler oluşturabilir. Bu yönergeler, kodun hala doğru çalıştığından emin olmak için bir çalışma zamanı denetimi tarafından korunur. Örneğin, derlerken `/arch:SSE2`SSE 4.2 yönergeleri dağıtılabilir. Çalışma zamanı denetimi, SSE 4.2 'ın hedef işlemcide kullanılabilir olduğunu doğrular ve işlemci bu yönergeleri desteklemiyorsa, döngünün SSE olmayan bir sürümüne atlar.

Varsayılan olarak, otomatik Vektörleştirici etkindir. Vektörleştirme altında kodunuzun performansını karşılaştırmak istiyorsanız, belirli bir döngünün vektörleştirilmesini devre dışı bırakmak için [#pragma döngüsünü (no_vector)](../preprocessor/loop.md) kullanabilirsiniz.

```cpp
#pragma loop(no_vector)
for (int i = 0; i < 1000; ++i)
   A[i] = B[i] + C[i];
```

Tüm [pragma yönergelerinde](../preprocessor/pragma-directives-and-the-pragma-keyword.md)olduğu gibi, alternatif pragma sözdizimi `__pragma(loop(no_vector))` de desteklenir.

Otomatik paralelleştirme sayesinde, [/Qvec-report (otomatik Vektörleştirici raporlama düzeyi)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md) komut satırı seçeneğini, yalnızca`/Qvec-report:1`başarıyla vektör haline getirilmiş döngüleri veya hem başarıyla hem de başarılı ve başarısız vektörleştirilmiş döngüleri`/Qvec-report:2`raporlamak için belirtebilirsiniz.

Neden kodları ve iletileri hakkında daha fazla bilgi için bkz. [Vektörtorizer ve paralelleştirme iletileri](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).

Vektörleştirici 'in uygulamada nasıl çalıştığını gösteren bir örnek için, bkz [. Proje Austin Bölüm 2/6: sayfa](https://devblogs.microsoft.com/cppblog/project-austin-part-2-of-6-page-curling/) oluşturma

## <a name="see-also"></a>Ayrıca bkz.

[loop](../preprocessor/loop.md)<br/>
[Yerel kodda paralel programlama](/archive/blogs/nativeconcurrency)<br/>
[/Qpar (Otomatik Paralel Hale Getirici)](../build/reference/qpar-auto-parallelizer.md)<br/>
[/Qpar-rapor (Otomatik Paralel Hale Getirici Raporlama Düzeyi)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md)<br/>
[/Qvec-report (otomatik Vektörleştirici raporlama düzeyi)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md)<br/>
[Vektörleştirici ve paralelleştirme Iletileri](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)
