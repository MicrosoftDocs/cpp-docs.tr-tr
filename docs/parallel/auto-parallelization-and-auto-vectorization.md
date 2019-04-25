---
title: Otomatik Paralelleştirme ve Otomatik Vektörleştirme
ms.date: 11/04/2016
ms.assetid: ec71583a-287b-4599-8767-1d255e080fe3
ms.openlocfilehash: 018289bc9499aee8d1739ebeed0c1cb847769a08
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62236705"
---
# <a name="auto-parallelization-and-auto-vectorization"></a>Otomatik Paralelleştirme ve Otomatik Vektörleştirme

Otomatik paralel hale getirici ve otomatik vektör hale getirici, kodunuzda döngüler için otomatik performans artışı sağlamak üzere tasarlanmıştır.

## <a name="auto-parallelizer"></a>Otomatik paralel hale getirici

[/Qpar](../build/reference/qpar-auto-parallelizer.md) derleyici anahtarı sağlayan *otomatik paralelleştirme* kodunuzda döngüsü. Bu bayrak, mevcut kodları değiştirmeden belirttiğinizde, derleyicinin paralelleştirme ' yararlanabilir döngüler bulmak için kodu değerlendirir. Fark edebilirsiniz çünkü çok yapan döngüler çalışır ve bu nedenle paralelleştirme yararlı olmaz ve gereksiz paralelleştirme her iş parçacığı havuzu UNICODE neden olabileceğini çünkü ek eşitleme veya diğer işleme yavaş eğilimindedir performansı geliştirecek yerine derleyici bunu parallelizes döngüler seçme içinde koruyucu. Örneğin, üst sınır döngü derleme zamanında bilinmiyor aşağıdaki örneği göz önünde bulundurun:

```cpp
void loop_test(int u) {
   for (int i=0; i<u; ++i)
      A[i] = B[i] * C[i];
}
```

Çünkü `u` küçük bir değer olabilir, derleyici otomatik olarak bu döngüyü paralel hale olmaz. Ancak, yine de paralel, bildiğiniz isteyebileceğiniz `u` her zaman büyük olacaktır. Otomatik paralelleştirme etkinleştirmek üzere belirtin [#pragma loop(hint_parallel(n))](../preprocessor/loop.md)burada `n` arasında paralel hale getirmek için iş parçacığı sayısıdır. Aşağıdaki örnekte, derleyici, 8 iş parçacığı arasında döngüyü paralel hale dener.

```cpp
void loop_test(int u) {
#pragma loop(hint_parallel(8))
   for (int i=0; i<u; ++i)
      A[i] = B[i] * C[i];
}
```

Tüm olduğu gibi [pragma yönergeleri](../preprocessor/pragma-directives-and-the-pragma-keyword.md), alternatif pragma söz dizimi `__pragma(loop(hint_parallel(n)))` de desteklenir.

İstediğiniz olsa bile, derleyici paralel hale getirmek olamaz bazı döngüleri vardır. Örnek buradadır:

```cpp
#pragma loop(hint_parallel(8))
for (int i=0; i<upper_bound(); ++i)
    A[i] = B[i] * C[i];
```

İşlev `upper_bound()` her çağrıldığında değişebilir. Üst sınır bilinen olduğundan derleyici neden bunu bu döngüyü paralel hale olamaz açıklayan bir tanılama iletisi gönderebilir. Aşağıdaki örnek, bir döngüyü paralel hale, bir döngüyü paralel hale, komut istemini ve derleyici çıkışını her komut satırı seçeneği için kullanılacak derleyici sözdizimini gösterir:

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

Bu komutu kullanarak derleme:

`cl d:\myproject\mylooptest.cpp /O2 /Qpar /Qpar-report:1`

Bu çıktıyı oluşturur:

```Output
--- Analyzing function: void __cdecl test(void)
d:\myproject\mytest.cpp(4) : loop parallelized
```

Bu komutu kullanarak derleme:

`cl d:\myproject\mylooptest.cpp /O2 /Qpar /Qpar-report:2`

Bu çıktıyı oluşturur:

```Output
--- Analyzing function: void __cdecl test(void)
d:\myproject\mytest.cpp(4) : loop parallelized
d:\myproject\mytest.cpp(4) : loop not parallelized due to reason '1008'
```

Farklı ikisi arasındaki fark çıkışında [/Qpar-report (otomatik paralel hale getirici raporlama düzeyi)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md) seçenekleri. `/Qpar-report:1` yalnızca başarıyla paralel döngüler için paralel hale getirici iletileri çıkarır. `/Qpar-report:2` hem başarılı ve başarısız döngü parallelizations için paralel hale getirici iletileri çıkarır.

Neden kodları ve iletiler hakkında daha fazla bilgi için bkz. [vektör yapıcı ve paralel hale getirici iletileri](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).

## <a name="auto-vectorizer"></a>Otomatik vektör hale getirici

Otomatik vektör hale getirici Döngülerde kodunuzu analiz eder ve mümkünse, yönergeleri ve vektör kayıt hedef bilgisayarda, yürütülecek kullanır. Bu, kodunuzun performansını artırabilir. Derleyici, SSE2 AVX ve AVX2 yönergeleri Intel ya da AMD işlemcileri veya ARM işlemcileri NEON yönergeler hedefleyen göre [/arch](../build/reference/arch-minimum-cpu-architecture.md) geçin.

Otomatik vektör hale getirici tarafından belirtilenden farklı yönergeleri oluşturabilir `/arch` geçin. Bu yönergeler, kod hala düzgün çalıştığından emin olmak için çalışma zamanı denetimi tarafından korunan. Örneğin, derleme yaptığınızda `/arch:SSE2`, SSE4.2 yönerge yayılır. Bir çalışma zamanı denetimi SSE4.2 hedef işlemci üzerinde kullanılabilir olduğunu ve bir döngünün SSE4.2 olmayan sürümüne işlemci bu yönergeleri desteklemiyorsa atlar olduğunu doğrular.

Varsayılan olarak, otomatik vektör hale getirici etkinleştirilir. Vektörleştirme altındaki kodunuzun performansını karşılaştırmak istiyorsanız, kullanabileceğiniz [#pragma loop(no_vector)](../preprocessor/loop.md) herhangi belirli bir döngü vektörleştirme devre dışı bırakmak için.

```cpp
#pragma loop(no_vector)
for (int i = 0; i < 1000; ++i)
   A[i] = B[i] + C[i];
```

Tüm olduğu gibi [pragma yönergeleri](../preprocessor/pragma-directives-and-the-pragma-keyword.md), alternatif pragma söz dizimi `__pragma(loop(no_vector))` de desteklenir.

Otomatik paralel hale getirici ile belirttiğiniz [/Qvec-report (otomatik vektör hale getirici raporlama düzeyi)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md) başarıyla bildirmek için komut satırı seçeneği yalnızca döngü vektörleştirildi —`/Qvec-report:1`— veya her ikisi de başarıyla ve başarısız, döngü vektörleştirildi —`/Qvec-report:2`).

Neden kodları ve iletiler hakkında daha fazla bilgi için bkz. [vektör yapıcı ve paralel hale getirici iletileri](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).

Vektör hale getirici uygulamada nasıl çalıştığını gösteren bir örnek için bkz [proje Austin Kısım 2 / 6: Curling sayfası](http://blogs.msdn.com/b/vcblog/archive/2012/09/27/10348494.aspx)

## <a name="see-also"></a>Ayrıca bkz.

[loop](../preprocessor/loop.md)<br/>
[Yerel kodda paralel programlama](http://go.microsoft.com/fwlink/p/?linkid=263662)<br/>
[/Qpar (Otomatik Paralel Hale Getirici)](../build/reference/qpar-auto-parallelizer.md)<br/>
[/Qpar-report (Otomatik Paralel Hale Getirici Raporlama Düzeyi)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md)<br/>
[/Qvec-report (Otomatik Vektör Hale Getirici Raporlama Düzeyi)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md)<br/>
[Vektör Yapıcı ve Paralel Hale Getirici İletileri](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)
