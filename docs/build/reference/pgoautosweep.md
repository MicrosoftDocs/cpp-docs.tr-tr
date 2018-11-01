---
title: PgoAutoSweep
ms.date: 03/14/2018
f1_keywords:
- PgoAutoSweep
- PogoAutoSweepA
- PogoAutoSweepW
ms.openlocfilehash: 356504da91a6778b5e873ca218df01944461d59c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456647"
---
# <a name="pgoautosweep"></a>PgoAutoSweep

`PgoAutoSweep` Geçerli profil sayaç bilgileri, bir dosyaya kaydeder ve sonra sayaçları sıfırlar. Profil temelli iyileştirme .pgc dosyası iyileştirme yapı daha sonra kullanmak için çalışan programın tüm profil verilerini yazmak eğitim sırasında işlevini kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
void PgoAutoSweep(const char* name);    // ANSI/MBCS
void PgoAutoSweep(const wchar_t* name); // UNICODE
```

### <a name="parameters"></a>Parametreler

*Adı*<br/>
Kaydedilen .pgc dosyası için bir tanımlayıcı dizesi.

## <a name="remarks"></a>Açıklamalar

Çağırabilirsiniz `PgoAutoSweep` kaydetmek ve uygulama yürütme sırasında herhangi bir noktada profil verilerini sıfırlamak için uygulamanızdan. İzleme eklenmiş bir yapıda `PgoAutoSweep` profili sayaçları sıfırlar geçerli profil oluşturma verilerini yakalar ve bir dosyaya kaydeder. Arama eşdeğerdir [pgosweep](pgosweep.md) yürütülebilir dosyanın belirli bir noktada komutu. En iyi duruma getirilmiş bir yapıda `PgoAutoSweep` bir İşlemsiz olduğu.

Profil sayaç verileri, adlı bir dosyaya yerleştirilir *base_name*-*adı*! *değer*.pgc, burada *base_name* yürütülebilir dosyanın temel adı *adı* parametresi için geçirilen `PgoAutoSweep`, ve *değer* Dosya adı çakışmalarını önlemek için genellikle bir düz olarak artan numarası, benzersiz bir değer var.

Tarafından oluşturulan .pgc dosyaları `PgoAutoSweep` en iyi duruma getirilmiş bir yürütülebilir dosyayı oluşturmak için kullanılacak bir .pgd dosyası birleştirilmesi gerekir. Kullanabileceğiniz [pgomgr](pgomgr.md) birleştirme işlemini gerçekleştirmek için komutu.

Kullanarak iyileştirme yapı sırasında bağlayıcıya birleştirilmiş bir .pgd dosyası adını geçirebilirsiniz **PGD =**_filename_ bağımsız değişkeni [/USEPROFILE](useprofile.md) bağlayıcı seçeneğini veya kullanım dışı kullanarak **/PGD** bağlayıcı seçeneği. Adlı bir dosyaya .pgc dosyaları birleştirme durumunda *base_name*.pgd, değil dosya komut satırında belirtmeniz gerekir çünkü bağlayıcı varsayılan olarak bu dosyanın adını alır.

`PgoAutoSweep` İşlevi, iş parçacığı güvenliği ayarı belirtilen işaretlenmiş yapımda oluşturulduğunda tutar. Varsayılan ayarı kullanın veya belirtirseniz **NOEXACT** bağımsız değişkeni [/genprofıle veya fastgenprofıle]() bağlayıcı seçeneği çağrılar `PgoAutoSweep` iş parçacığı açısından güvenli değildir. **EXACT** bağımsız değişkeni oluşturur, bir iş parçacığı açısından güvenli ve daha doğru ancak daha yavaş, izleme eklenmiş çalıştırılabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`PgoAutoSweep`|\<pgobootrun.h>|

Yürütülebilir dosyayı bağlı kitaplıkları pgobootrun.lib dosya içermesi gerekir. Bu dosyayı Visual Studio yüklemenizin desteklenen her mimari için VC kitaplıkları dizininde yer alır.

## <a name="example"></a>Örnek

Kullanan aşağıdaki örnekte `PgoAutoSweep` iki oluşturmak için. PGC dosyaları yürütme sırasında farklı noktalarda. İlk kadar çalışma zamanı davranışını tanımlayan veriler içeren `count` 3'e eşittir ve ikinci hemen önce uygulama sonlandırma kadar bu noktadan sonra toplanan verileri içerir.

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

Bir geliştirici Komut İstemi'nde, şu komutu kullanarak bir nesne dosyası için kodu derleyin:

`cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp`

Ardından bu komutu kullanarak eğitim için izleme eklenmiş bir derleme oluşturur:

`link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj`

Eğitim verileri yakalamak için izleme eklenmiş çalıştırılabilir çalıştırın. Yapılan çağrılar tarafından veri çıkışı `PgoAutoSweep` pgoautosweep func1 adlı dosyalarında kaydedildi! 1.pgc ve pgoautosweep func2! 1.pgc. Çalışırken programın çıkışı şu şekilde görünmelidir:

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

Çalıştırarak profili eğitim veritabanına kaydedilmiş verilerle birleştirmek **pgomgr** komutu:

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

Artık iyileştirilmiş bir derleme oluşturmak için bu eğitim verilerini kullanabilirsiniz. En iyi duruma getirilmiş çalıştırılabilir dosyayı oluşturmak için bu komutu kullanın:

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

[Profil Temelli İyileştirmeler](profile-guided-optimizations.md)<br/>
[pgosweep](pgosweep.md)<br/>
