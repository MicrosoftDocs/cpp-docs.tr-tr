---
title: SIMD Uzantısı
ms.date: 03/20/2019
helpviewer_keywords:
- SIMD
- OpenMP in Visual C++, new features
- explicit parallelization, new features
ms.openlocfilehash: 0a7f1142a3a432628795341f4885b76a5c144990
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366459"
---
# <a name="simd-extension"></a>SIMD Uzantısı

Visual C++şu anda OpenMP 2.0 standardını destekler, ancak Visual Studio 2019 da simd işlevselliği sunar.

> [!NOTE]
> SIMD kullanmak için, anahtarı `-openmp:experimental` kullanırken kullanılabilir olmayan ek OpenMP `-openmp` özellikleri sağlayan anahtarı ile derle.
>
> Anahtar `-openmp:experimental` subsumes `-openmp`, tüm OpenMP 2.0 özellikleri kullanımı dahil anlamına gelir.

Daha fazla bilgi için [Visual Studio'da C++ OpenMP'a SIMD Uzantısı'na](https://devblogs.microsoft.com/cppblog/simd-extension-to-c-openmp-in-visual-studio/)bakın.

## <a name="openmp-simd-in-visual-c"></a>Visual C++'da OpenMP SIMD

OpenMP 4.0 standardında tanıtılan OpenMP SIMD, vektör dostu döngüler yapmayı hedefler. Bir döngüden `simd` önce yönergeleri kullanarak, derleyici vektör bağımlılıklarını yok sayabilir, döngüyü olabildiğince vektör dostu yapabilir ve kullanıcıların aynı anda birden çok döngü yinelemesi yapma niyetine saygı duyabilir.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Visual C++gibi `#pragma vector` benzer non-OpenMP döngü `#pragma ivdep`pragmas sağlar ve , Ancak OpenMP SIMD ile, derleyici gibi daha fazlasını yapabilirsiniz:

- Her zaman mevcut vektör bağımlılıklarını yok saymak için izin verilir.
- `/fp:fast`döngü içinde etkindir.
- Fonksiyon çağrıları ile dış döngüler ve döngüler vektör dostudur.
- İç içe döngüler tek bir döngü halinde birleşerek vektör dostu hale getirilebilir.
- Kaba taneli çok dişli ve ince taneli vektörler `#pragma omp for simd` etkinleştirmek için hibrid ivme.  

Vektör dostu döngüler için, vektör destek günlüğü anahtarı kullanmadığınız sürece derleyici sessiz kalır:

```cmd
    cl -O2 -openmp:experimental -Qvec-report:2 mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(96) : info C5001: Omp simd loop vectorized
```

Vektör dostu olmayan döngüler için derleyici her biri bir iletiyi yayınlar:

```cmd
    cl -O2 -openmp:experimental mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
```

### <a name="clauses"></a>Yan tümceler

OpenMP SIMD yönergesi vektör desteğini geliştirmek için aşağıdaki yan tümceleri de alabilir:

|Yönergesi|Açıklama|
|---|---|
|`simdlen(length)`|Vektör şeritlerinin sayısını belirtin.|
|`safelen(length)`|Vektör bağımlılık mesafesini belirtin.|
|`linear(list[ : linear-step]`)|Döngü tümevarım değişkeninden dizi aboneliğine doğrusal eşleme.|
|`aligned(list[ : alignment])`|Verilerin hizalanması.|
|`private(list)`|Veri özelleştirmesi belirtin.|
|`lastprivate(list)`|Son yinelemeden son değeri olan veri özelleştirmesini belirtin.|
|`reduction(reduction-identifier:list)`|Özelleştirilmiş azaltma işlemleri belirtin.|
|`collapse(n)`|Birleştirme döngüsü yuvası.|

> [!NOTE]
> Etkili olmayan SIMD yan tümceleri ayrıştıve derleyici tarafından bir uyarı ile yoksayılır.
>
> Örneğin, aşağıdaki kodun kullanımı bir uyarı yayınlar:
>
> ```c
>    #pragma omp simd simdlen(8)
>    for (i = 0; i < count; i++)
>    {
>        a[i] = a[i-1] + 1;
>        b[i] = *c + 1;
>        bar(i);
>    }
> ```
>
> ```Output
>    warning C4849: OpenMP 'simdlen' clause ignored in 'simd' directive
> ```

### <a name="example"></a>Örnek
  
OpenMP SIMD yönergesi, kullanıcılara derleyicinin döngüleri vektör dostu hale getirmesini dikte etmek için bir yol sağlar. OpenMP SIMD yönergesi ile bir döngüek açıklama yaparak, kullanıcılar aynı anda yürütülmesi birden çok döngü yinelemeleri olmasını planlıyoruz.

Örneğin, aşağıdaki döngü OpenMP SIMD yönergesi ile açıklamalı. Döngü yinelemeleri arasında mükemmel bir paralellik yoktur, çünkü a[i]'den [i-1]'e geriye doğru bir bağımlılık vardır, ancak SIMD yönergesi sayesinde derleyici nin ilk ifadenin ardışık yinelemelerini tek bir vektör yönergesine paketleyip paralel olarak çalıştırmasına izin verilir.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Bu nedenle, derleyici her özgün döngü yinelemesinin sıralı davranışını tuttuğundan, döngünün aşağıdaki dönüştürülmüş vektör formu **yasaldır.** Başka bir `a[i]` deyişle, `a[-1]`sonra `b[i]` yürütülür , sonra `a[i]` ve arama son `bar` olur.

```c
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        b[i:i+3] = *c + 1;
        bar(i);
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

Bellek başvurucunun `*c` döngüdışına taşınması **yasal değildir.** `a[i]` `b[i]` Sıralı bağımlılığı kırıyorsa, tek bir orijinal yineleme içindeki ifadeleri yeniden sıralamak da yasal değildir. Örneğin, aşağıdaki dönüştürülmüş döngü yasal değildir:

```c
    c = b;
    t = *c;
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        bar(i);            // illegal to reorder if bar[i] depends on b[i]
        b[i:i+3] = t + 1;  // illegal to move *c out of the loop
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

## <a name="see-also"></a>Ayrıca bkz.

[/openmp (OpenMP 2.0 Desteği etkinleştir)](../../build/reference/openmp-enable-openmp-2-0-support.md)<br/>
