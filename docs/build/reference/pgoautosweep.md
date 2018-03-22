---
title: PgoAutoSweep | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- PgoAutoSweep
- PogoAutoSweepA
- PogoAutoSweepW
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6b26eb95552594733fa0849c0df114676dc7a222
ms.sourcegitcommit: ee7d74683af7631441c8c7f65ef5ceceaee4a5ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="pgoautosweep"></a>PgoAutoSweep

`PgoAutoSweep` Geçerli profil sayaç bilgileri bir dosyaya kaydeder ve sayaçları sıfırlar. Profil temelli iyileştirme .pgc dosya iyileştirme derleme daha sonra kullanmak için çalışan programından tüm profil verilerini yazmak eğitim sırasında işlevini kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
void PgoAutoSweep(const char* name);    // ANSI/MBCS
void PgoAutoSweep(const wchar_t* name); // UNICODE
```

### <a name="parameters"></a>Parametreler

*Adı*<br/>
Kaydedilmiş .pgc dosya tanımlayan bir dize.

## <a name="remarks"></a>Açıklamalar

Çağırabilirsiniz `PgoAutoSweep` kaydetme ve uygulama yürütmesi sırasında herhangi bir noktada profil verileri sıfırlamak için uygulamanızdan. İzleme eklenmiş bir yapı içinde `PgoAutoSweep` geçerli profil oluşturma verileri yakalar, bir dosyaya kaydeder ve profil sayaçları sıfırlar. Arama eşdeğerdir [pgosweep](pgosweep.md) yürütülebilir dosyanın içindeki belirli bir noktada komutu. En iyi duruma getirilmiş bir yapı içinde `PgoAutoSweep` Hayır OP.

Kaydedilmiş profil sayaç verileri adındaki bir dosyada yerleştirilir *base_name*-*adı*! *değer*.pgc, burada *base_name* yürütülebilir temel adı *adı* parametresi için geçirilen `PgoAutoSweep`, ve *değeri* Dosya adı çakışmaları önlemek için genellikle artan numarası, benzersiz bir değer değil.

Tarafından oluşturulan .pgc dosyaları `PgoAutoSweep` en iyi duruma getirilmiş bir yürütülebilir dosya oluşturmak için kullanılacak bir .pgd dosyasına birleştirilmesi gerekir. Kullanabileceğiniz [pgomgr](pgomgr.md) birleştirme işlemini gerçekleştirmek için komutu.

Kullanarak en iyi duruma getirme derleme sırasında bağlayıcıya birleştirilmiş .pgd dosyasının adı geçirebilirsiniz **PGD =**_filename_ bağımsız değişkeni [/USEPROFILE](useprofile.md) bağlayıcı seçeneği ya da kullanım dışı kullanarak **/PGD** bağlayıcı seçeneği. Adlı bir dosyaya .pgc dosyaları birleştirme, *base_name*.pgd, gerek yoktur filename komut satırında belirttiğiniz bağlayıcı varsayılan olarak bu dosya adını oluşturan Çekmeleri olduğundan.

`PgoAutoSweep` İşlevi tutar iş parçacığı güvenliği ayarı belirtilen Araçlı derleme oluşturulduğunda. Varsayılan ayarı kullanın veya belirtirseniz **NOEXACT** bağımsız değişkeni [/GENPROFILE veya /FASTGENPROFILE]() bağlayıcı seçeneği çağrılar `PgoAutoSweep` iş parçacığı açısından güvenli değildir. **Tam** bağımsız değişkeni bir iş parçacığı açısından güvenli ve daha doğru ancak oluşturur yavaş, Araçlı çalıştırılabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`PgoAutoSweep`|\<pgobootrun.h>|

Yürütülebilir dosya bağlantılı kitaplıklarında pgobootrun.lib dosyası içermelidir. Bu dosyayı Visual Studio yüklemenizin desteklenen her mimari için VC kitaplıkları dizininde yer alır.

## <a name="example"></a>Örnek

Kullandığı aşağıdaki örnekte `PgoAutoSweep` iki oluşturmak için. Yürütme sırasında farklı noktalarda PGC dosyalar. İlk kadar çalışma zamanı davranışını tanımlar verileri içeren `count` 3'e eşittir ve ikinci uygulama sonlandırma kadar hemen önce bu noktadan sonra toplanan verileri içerir.

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

Geliştirici komut isteminde bu komutu kullanarak bir nesne dosyası için kod derleme:

`cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp`

Ardından bu komutu kullanarak eğitim için izleme eklenmiş bir derleme oluştur:

`link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj`

Eğitim verileri yakalamak için izleme eklenmiş yürütülebilir dosyayı çalıştırmak. Veri çıkışı yapılan çağrılar tarafından `PgoAutoSweep` pgoautosweep func1 adlı dosyalarda kaydedildi! 1.pgc ve pgoautosweep func2! 1.pgc. Çalışırken programın çıkışı aşağıdaki gibi görünmelidir:

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

Çalıştırarak bir profil eğitim veritabanına kaydedilen veri birleştirme **pgomgr** komutu:

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

Artık bu eğitim verileri en iyi duruma getirilmiş bir yapı oluşturmak için kullanabilirsiniz. En iyi duruma getirilmiş yürütülebilir dosyayı oluşturmak için bu komutu kullanın:

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
