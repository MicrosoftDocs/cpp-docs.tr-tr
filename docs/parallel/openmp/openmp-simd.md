---
title: SIMD Uzantısı
ms.date: 03/20/2019
helpviewer_keywords:
- SIMD
- OpenMP in Visual C++, new features
- explicit parallelization, new features
ms.openlocfilehash: 52402aa553c6d68d3073aba26ecac7b784522ee9
ms.sourcegitcommit: 14b292596bc9b9b883a9c58cd3e366b282a1f7b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60125164"
---
# <a name="simd-extension"></a>SIMD Uzantısı

Görsel C++ Visual Studio 2019 SIMD işlevi de sunar ancak şu anda OpenMP 2.0 standart destekler.

> [!NOTE]
> SIMD kullanmak için derleme `-openmp:experimental` kullanırken mevcut olmayan ek OpenMP özellikler sağlayan anahtar `-openmp` geçin.
>
> `-openmp:experimental` Anahtar subsumes `-openmp`, kullanımını edilen tüm OpenMP 2.0 özelliklerini anlamına gelir.

Daha fazla bilgi için [SIMD Uzantısı C++ Visual Studio'daki OpenMP](https://devblogs.microsoft.com/cppblog/simd-extension-to-c-openmp-in-visual-studio/).

## <a name="openmp-simd-in-visual-c"></a>OpenMP SIMD görseldeC++

OpenMP SIMD, standart, OpenMP 4.0 döngüleri vektör kullanımı kolay hale hedefleri sunulan. Kullanarak `simd` döngü önce yönergesi, derleyici vektör bağımlılıklarını yoksayma, döngü olarak vektör kullanımı kolay mümkün olduğunca yapın ve aynı anda birden çok döngü yinelemesi için kullanıcıların engellemekse dikkate.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Görsel C++ benzer olmayan bir OpenMP döngüsünü pragmaları ister sağlar `#pragma vector` ve `#pragma ivdep`OpenMP SIMD ile derleyici hakkında daha fazla bilgi gibi yapabilirsiniz ancak:

- Mevcut vektör bağımlılıklarını yoksayma için her zaman izin verilir.
- `/fp:fast` döngü içinde etkinleştirilir.
- Dış döngü ve işlev çağrıları ile döngüleri vektör dostu.
- İç içe döngüleri, tek bir döngüde birleştirilen ve vektör kolay yapılır.
- İle karma hızlandırma `#pragma omp for simd` parçalı çoklu iş parçacığı ve ayrıntılı vektörleri etkinleştirmek için.  

Destek vektörü log anahtarı kullanmadığınız sürece for döngüleri vektör kullanımı kolay, derleyici sessiz kalır:

```cmd
    cl -O2 -openmp:experimental -Qvec-report:2 mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(96) : info C5001: Omp simd loop vectorized
```

For döngüleri vektör kolay, derleyici her bir iletiyi görüntüler:

```cmd
    cl -O2 -openmp:experimental mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
```

### <a name="clauses"></a>Tümceler

SIMD OpenMP yönergesi, destek vektörü artırmak için aşağıdaki yan tümceleri de alabilir:

|Yönergesi|Açıklama|
|---|---|
|`simdlen(length)`|Vektör kulvarları sayısını belirtin.|
|`safelen(length)`|Vektör bağımlılık uzaklığı belirtir.|
|`linear(list[ : linear-step]`)|Döngü endüksiyon değişkeni doğrusal eşlemesinden dizi aboneliğe.|
|`aligned(list[ : alignment])`|Veri hizalama.|
|`private(list)`|Veri privatization belirtin.|
|`lastprivate(list)`|Son yineleme son değeri ile veri privatization belirtin.|
|`reduction(reduction-identifier:list)`|Özelleştirilmiş azaltma işlemleri belirtin.|
|`collapse(n)`|Döngü iç içe birleşim.|

> [!NOTE]
> Etkin olmayan SIMD yan tümceleri ayrıştırılır ve bir uyarı derleyici tarafından yok sayıldı.
>
> Örneğin, aşağıdaki kod sorunlarını uyarı kullanın:
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
  
SIMD OpenMP yönergesi kullanıcılar dikte derleyici yapma döngüleri vektör kullanımı kolay bir yol sağlar. Kullanıcılar, bir döngü SIMD OpenMP yönergesi ile açıklama ekleyerek aynı anda birden çok döngü yinelemesi sunmayı planlıyoruz.

Örneğin, aşağıdaki döngü SIMD OpenMP yönergesi ile açıklanıyor. Geriye dönük bağımlılık [i-1], ancak derleyicinin hala bir vektör yönerge ilk ifadesine ardışık yinelemeleri paketi ve çalıştırmasına izin verilmeyen SIMD yönergesi nedeniyle [i] öğesinden olduğundan döngü yinelemesi arasında kusursuz hiçbir paralellik olduğu bunları paralel.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Bu nedenle, aşağıdaki dönüştürülmüş vektör döngü biçimindedir **yasal** derleyici özgün her döngü yinelemesinin sıralı davranışını tuttuğu. Diğer bir deyişle, `a[i]` sonra yürütülür `a[-1]`, `b[i]` sonra `a[i]` ve çağrısı `bar` son olur.

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

Sahip **değil yasal** bellek başvuru taşımak `*c` diğer adına sahip olabilir, döngünün dışında `a[i]` veya `b[i]`. Ayrıca sıralı bağımlılık keserse özgün bir yinelemedeki deyimleri yeniden sıralamak için geçerli değil. Örneğin, aşağıdaki dönüştürülmüş döngü geçerli değildir:

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

[/openmp (OpenMP 2.0 Desteğini Etkinleştir)](../../build/reference/openmp-enable-openmp-2-0-support.md)<br/>
