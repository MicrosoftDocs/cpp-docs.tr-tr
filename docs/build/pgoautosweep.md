---
description: 'Daha fazla bilgi edinin: Pgooto süpürme'
title: PgoAutoSweep
ms.date: 07/02/2019
f1_keywords:
- PgoAutoSweep
- PogoAutoSweepA
- PogoAutoSweepW
ms.openlocfilehash: 8310b86f8ef7db011ed7340cef4e42def79a0927
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179791"
---
# <a name="pgoautosweep"></a>PgoAutoSweep

`PgoAutoSweep` geçerli profil sayacı bilgilerini bir dosyaya kaydeder ve sonra sayaçları sıfırlar. Çalışan programdan `.pgc` daha sonra en iyi duruma getirme derlemesinde kullanmak üzere tüm profil verilerini bir dosyaya yazmak için profil temelli iyileştirme eğitimi sırasında işlevini kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
void PgoAutoSweep(const char* name);    // ANSI/MBCS
void PgoAutoSweep(const wchar_t* name); // UNICODE
```

### <a name="parameters"></a>Parametreler

*ada*<br/>
Kaydedilen dosya için tanımlayıcı dize `.pgc` .

## <a name="remarks"></a>Açıklamalar

Uygulama `PgoAutoSweep` yürütme sırasında herhangi bir noktada profil verilerini kaydetmek ve sıfırlamak için uygulamanızdan çağrı yapabilirsiniz. Belgelenmiş bir derlemede, `PgoAutoSweep` geçerli profil oluşturma verilerini yakalar, bir dosyaya kaydeder ve profil sayaçlarını sıfırlar. Bu, çalıştırılabilirinizdeki belirli bir noktada [pgosüpürme](pgosweep.md) komutunu çağırmanın eşdeğeridir. İyileştirilmiş bir derlemede, `PgoAutoSweep` işlem yapılmaz.

Kaydedilen profil sayaç verileri *base_name* adı adlı bir dosyaya yerleştirildi - !*value*. pgc, *base_name* çalıştırılabilir dosyanın temel adı, *adı* geçirilen parametredir `PgoAutoSweep` ve *değer* , dosya adı çakışmalarını engellemek için genellikle tek bir artan sayı olan benzersiz bir değerdir.

`.pgc`Tarafından oluşturulan dosyalar, `PgoAutoSweep` `.pgd` iyileştirilmiş bir yürütülebilir dosya oluşturmak için kullanılacak bir dosyada birleştirilmelidir. Birleştirme işlemini gerçekleştirmek için [Pgomgr](pgomgr.md) komutunu kullanabilirsiniz.

`.pgd`En iyi duruma getirme derlemesi sırasında, ' ' bir dosya adı bağımsız değişkeni olan [/useprofile](reference/useprofile.md) bağlayıcı seçeneğine  veya kullanım dışı **/PGD** bağlayıcı seçeneğini kullanarak, birleştirilmiş dosyanın adını bağlayıcıya geçirebilirsiniz. `.pgc`Dosyaları *base_name*. pgd adlı bir dosyada birleştirirseniz, bağlayıcı varsayılan olarak bu dosya adını sağladığından komut satırında dosya adını belirtmeniz gerekmez.

`PgoAutoSweep`İşlevi, belgelenmiş derleme oluşturulduğunda belirtilen iş parçacığı güvenliği ayarını korur. Varsayılan ayarı kullanır veya [/Genprofile veya/FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) bağlayıcı seçeneği için **bir bağımsız değişkeni** belirtirseniz, çağrıları `PgoAutoSweep` iş parçacığı açısından güvenli değildir. **Tam** bağımsız değişken bir iş parçacığı güvenli ve daha doğru, ancak daha yavaş, belgelenmiş yürütülebilir dosya oluşturur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`PgoAutoSweep`|\<pgobootrun.h>|

Yürütülebilir dosya, bağlantılı kitaplıklarda pgobootrun. lib dosyasını içermelidir. Bu dosya, desteklenen her mimari için VC kitaplıkları dizininde bulunan Visual Studio yüklemenize dahildir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `PgoAutoSweep` `.pgc` yürütme sırasında farklı noktalarda iki dosya oluşturmak için kullanır. İlki, 3 ' e eşit olana kadar çalışma zamanı davranışını açıklayan verileri içerir `count` ve ikincisi, uygulama sonlandırmasına kadar bu noktadan sonra toplanan verileri içerir.

```cpp
// pgoautosweep.cpp
// Compile by using: cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp
// Link to instrument: link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj
// Run to generate data: pgoautosweep
// Merge data by using command line pgomgr tool:
// pgomgr /merge pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc pgoautosweep.pgd
// Link to optimize: link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj

#include <iostream>
#include <windows.h>
#include <pgobootrun.h>

void func2(int count)
{
    std::cout << "hello from func2 " << count << std::endl;
    Sleep(2000);
}

void func1(int count)
{
    std::cout << "hello from func1 " << count << std::endl;
    Sleep(2000);
}

int main()
{
    int count = 10;
    while (count--)
    {
        if (count < 3)
            func2(count);
        else
        {
            func1(count);
            if (count == 3)
            {
                PgoAutoSweep("func1");
            }
        }
    }
    PgoAutoSweep("func2");
}
```

Bir geliştirici komut isteminde, aşağıdaki komutu kullanarak kodu bir nesne dosyasına derleyin:

`cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp`

Ardından şu komutu kullanarak eğitim için bir belgelenmiş derleme oluşturun:

`link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj`

Eğitim verilerini yakalamak için belgelenmiş çalıştırılabiliri çalıştırın. Çağrıları tarafından yapılan veri çıktısı `PgoAutoSweep` pgootomatik tarama-func1! 1. pgc ve pgootomatik tarama-Func2! 1. pgc adlı dosyalara kaydedilir. Programın çıktısı, çalıştığı şekilde şöyle görünmelidir:

```Output
hello from func1 9
hello from func1 8
hello from func1 7
hello from func1 6
hello from func1 5
hello from func1 4
hello from func1 3
hello from func2 2
hello from func2 1
hello from func2 0
```

**Pgomgr** komutunu çalıştırarak kaydedilen verileri bir profil eğitimi veritabanına birleştirin:

`pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc`

Bu komutun çıktısı şuna benzer:

```Output
Microsoft (R) Profile Guided Optimization Manager 14.13.26128.0
Copyright (C) Microsoft Corporation. All rights reserved.

Merging pgoautosweep-func1!1.pgc
pgoautosweep-func1!1.pgc: Used  3.8% (22304 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
Merging pgoautosweep-func2!1.pgc
pgoautosweep-func2!1.pgc: Used  3.8% (22424 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
```

Artık bu eğitim verilerini, iyileştirilmiş bir yapı oluşturmak için kullanabilirsiniz. En iyileştirilmiş yürütülebilir dosyayı oluşturmak için bu komutu kullanın:

`link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj`

```Output
Microsoft (R) Incremental Linker Version 14.13.26128.0
Copyright (C) Microsoft Corporation.  All rights reserved.

Merging pgoautosweep!1.pgc
pgoautosweep!1.pgc: Used  3.9% (22904 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
  Reading PGD file 1: pgoautosweep.pgd
Generating code

0 of 0 ( 0.0%) original invalid call sites were matched.
0 new call sites were added.
294 of 294 (100.00%) profiled functions will be compiled for speed
348 of 1239 inline instances were from dead/cold paths
294 of 294 functions (100.0%) were optimized using profile data
16870 of 16870 instructions (100.0%) were optimized using profile data
Finished generating code
```

## <a name="see-also"></a>Ayrıca bkz.

[Profil temelli Iyileştirmeler](profile-guided-optimizations.md)<br/>
[pgosweep](pgosweep.md)<br/>
