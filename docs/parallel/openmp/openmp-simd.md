---
description: 'Şu konuda daha fazla bilgi edinin: SıMD uzantısı'
title: SIMD Uzantısı
ms.date: 03/20/2019
helpviewer_keywords:
- SIMD
- OpenMP in Visual C++, new features
- explicit parallelization, new features
ms.openlocfilehash: 58a3f29002c4e517a2019454dfe741dfb5352a3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342432"
---
# <a name="simd-extension"></a>SIMD Uzantısı

Visual C++ Şu anda OpenMP 2,0 standardını destekliyor ancak Visual Studio 2019 artık SıMD işlevselliği sunmaktadır.

> [!NOTE]
> SıMD 'yi kullanmak için, `-openmp:experimental` anahtarı kullanırken ek OpenMP özelliklerinin kullanılamaz olmasını sağlayan anahtarla derleyin `-openmp` .
>
> `-openmp:experimental`Anahtar alt öğeleri `-openmp` , tüm OpenMP 2,0 özelliklerinin kullanımına dahil olduğu anlamına gelir.

Daha fazla bilgi için bkz. [Visual Studio 'Da SIMD uzantısı C++ OpenMP](https://devblogs.microsoft.com/cppblog/simd-extension-to-c-openmp-in-visual-studio/).

## <a name="openmp-simd-in-visual-c"></a>Visual C++ OpenMP SıMD

OpenMP 4,0 standardında sunulan OpenMP SıMD, vektör kullanımı kolay döngüler yapmayı hedefler. `simd`Bir döngüden önce yönergesini kullanarak, derleyici vektör bağımlılıklarını yoksayabilir, döngüyü mümkün olduğunca vektör açısından kolay hale getirir ve kullanıcıların amaç 'nin aynı anda birden çok döngü yinelemesi olmasını sağlar.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Visual C++ benzer bir OpenMP olmayan döngü pragmaları sağlar `#pragma vector` ve `#pragma ivdep` ancak OpenMP SIMD ile, derleyici daha fazlasını yapabilir, örneğin:

- Her zaman mevcut vektör bağımlılıklarını yok saymaya izin verilir.
- `/fp:fast` döngü içinde etkin.
- İşlev çağrılarına sahip dış döngüler ve döngüler vektör kullanımı kolay.
- İç içe döngüler tek bir döngüyle birleştirilebilir ve vektör kullanımı kolay hale getirilebilir.
- `#pragma omp for simd`Parçalı, çok iş parçacıklı ve hassas vektörlerle karma hızlandırma sağlar.  

Vektör kullanımı kolay döngüler için, vektör desteği günlük anahtarı kullanmadığınız sürece derleyici sessiz kalır:

```cmd
    cl -O2 -openmp:experimental -Qvec-report:2 mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(96) : info C5001: Omp simd loop vectorized
```

Vektör kullanımı kolay olmayan döngüler için, derleyici her bir iletiyi yayınlar:

```cmd
    cl -O2 -openmp:experimental mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
```

### <a name="clauses"></a>Yan tümceler

OpenMP SıMD yönergesi, vektör desteğini geliştirmek için aşağıdaki yan tümceleri de alabilir:

|Deki|Açıklama|
|---|---|
|`simdlen(length)`|Vektör kulvarları sayısını belirtin.|
|`safelen(length)`|Vektör bağımlılığı uzaklığını belirtin.|
|`linear(list[ : linear-step]`)|Döngüdeki doğrusal eşleme, dizi aboneliğine.|
|`aligned(list[ : alignment])`|Verilerin hizalaması.|
|`private(list)`|Data limanların belirtin.|
|`lastprivate(list)`|Son yinelemeden son değer ile Data limanların belirtin.|
|`reduction(reduction-identifier:list)`|Özelleştirilmiş azaltma işlemlerini belirtin.|
|`collapse(n)`|Birleştirme döngüsü iç içe.|

> [!NOTE]
> Etkin olmayan SıMD yan tümceleri ayrıştırılır ve bir uyarı ile derleyici tarafından yok sayılır.
>
> Örneğin, aşağıdaki kodun kullanımı bir uyarı verir:
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
  
OpenMP SıMD yönergesi kullanıcılara derleyici oluşturma döngülerini vektör kullanımı için bir yol sağlar. OpenMP SıMD yönergesi ile bir döngüye açıklama ekleyerek birden çok döngü yinelemesi aynı anda yürütülür.

Örneğin, aşağıdaki döngüye OpenMP SıMD yönergesi ile açıklama eklenir. Bir [i] ile [i-1] arasında geriye doğru bir bağımlılık olduğundan, döngü yinelemeleri arasında kusursuz bir paralellik yoktur, ancak SıMD yönergesi nedeniyle derleyicinin ilk deyimin birbirini izleyen yinelemelerini tek bir vektör yönergesinde paketleyemedi ve bunları paralel olarak çalıştırmasına izin verilmeye devam etmektedir.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Bu nedenle, derleyici her bir özgün döngü yinelemesinin sıralı davranışını yaptığından, döngünün aşağıdaki dönüştürülmüş vektör formu **geçerlidir** . Diğer bir deyişle, öğesinden `a[i]` sonra, `a[-1]` `b[i]` `a[i]` ve çağrısı `bar` son gerçekleşmeden sonra yürütülür.

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

 `*c` Veya ile diğer adı varsa, bellek başvurusunu döngüden taşımak yasal değildir `a[i]` `b[i]` . Sıralı bağımlılığı kopararsa, deyimleri bir özgün yinelemede yeniden sıralamak yasal değildir. Örneğin, aşağıdaki dönüştürülmüş döngü geçerli değildir:

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

[/OpenMP (OpenMP 2,0 desteğini etkinleştir)](../../build/reference/openmp-enable-openmp-2-0-support.md)<br/>
