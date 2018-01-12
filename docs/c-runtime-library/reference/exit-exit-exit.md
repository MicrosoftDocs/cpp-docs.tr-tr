---
title: "Çıkış, _Exit, _exit | Microsoft Docs"
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _exit
- exit
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- Exit
- _exit
- process/exit
- process/_Exit
- stdlib/exit
- stdlib/_Exit
dev_langs: C++
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dbb54b756363da2069bbc4bface4e971fcab91e4
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="exit-exit-exit"></a>Çıkış, _Exit, _exit

Arama işlemi sonlandırır. `exit` İşlevi sonlandırır, temizleme sonrasında; `_exit` ve `_Exit` hemen sonlandır.

> [!NOTE]
> Bu yöntem, test etme veya senaryoları hata ayıklama bir evrensel Windows Platformu (UWP) uygulamasını, kapatmak için kullanmayın. Bir mağaza uygulamasını kapatmak için programlı veya UI yolu göre verilmez [Microsoft Store ilkeleri](/legal/windows/agreements/store-policies). Daha fazla bilgi için bkz: [UWP uygulama yaşam döngüsü](/windows/uwp/launch-resume/app-lifecycle). Windows 10 uygulamaları hakkında daha fazla bilgi için bkz: [nasıl yapılır kılavuzları için Windows 10 uygulamaları](http://go.microsoft.com/fwlink/p/?linkid=619133).

## <a name="syntax"></a>Sözdizimi

```C
void exit(
   int const status
);
void _Exit(
   int const status
);
void _exit( 
   int const status
);
```

### <a name="parameters"></a>Parametreler

_durumu_  
Durum kodu çıkın.

## <a name="remarks"></a>Açıklamalar

`exit`, `_Exit` Ve `_exit` işlevleri çağırma işlemi sonlandırılacak. `exit` İşlevi çağırır Yıkıcılar iş parçacığı yerel nesneler için daha sonra çağırır — son olarak ilk çıkar (LIFO) sırayla — tarafından kaydedilen işlevleri `atexit` ve `_onexit`ve işlem sona erdirmeden önce tüm dosya arabelleklerini alır. `_Exit` Ve `_exit` işlevleri sonlandırma işlemi iş parçacığı yerel nesneleri yok etme veya işlemeden `atexit` veya `_onexit` işlevler ve akış arabellekleri temizleme olmadan.

Ancak `exit`, `_Exit` ve `_exit` çağrıları değer'de bir değer döndürmeyen _durum_ işlemi çıktıktan sonra varsa ana bilgisayar ortamının veya bekleme çağırma işlemi, kullanılabilir hale getirilir. Genellikle, çağıran kümeleri _durum_ değer normal bir çıkış göstermek için 0 veya bir hata göstermek için başka bir değer. _Durum_ değeri işletim sistemi toplu komutuna kullanılabilir `ERRORLEVEL` ve iki sabitlerden biri tarafından temsil edilen: `EXIT_SUCCESS`, 0 değerini temsil eder veya `EXIT_FAILURE`, 1 değerini temsil eder.

`exit`, `_Exit`, `_exit`, `quick_exit`, `_cexit`, Ve `_c_exit` işlevleri gibi davranır.

|İşlev|Açıklama|
|--------------|-----------------|
|`exit`|Tam C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının için sağlanan durum kodu sağlar.|
|`_Exit`|En az C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının için sağlanan durum kodu sağlar.|
|`_exit`|En az C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının için sağlanan durum kodu sağlar.|
|`quick_exit`|Hızlı C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının için sağlanan durum kodu sağlar.|
|`_cexit`|Tam C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana döndürür. İşlemi Sonlandır değil.|
|`_c_exit`|En az C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana döndürür. İşlemi Sonlandır değil.|

Çağırdığınızda `exit`, `_Exit` veya `_exit` işlev çağrısı sırada mevcut geçici veya otomatik nesneleri için Yıkıcılar çağrılır değil. Tanımlı bir işlevde statik olmayan yerel bir nesne bir otomatik nesnesidir. Geçici bir nesne gibi bir işlev çağrısı tarafından döndürülen değer derleyici tarafından oluşturulan nesnedir. Arama yapmadan önce bir otomatik nesne yok etmek için `exit`, `_Exit`, veya `_exit`, açıkça yıkıcı nesne için aşağıda gösterildiği gibi çağırın:

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

Kullanmayın `DLL_PROCESS_ATTACH` çağırmak için `exit` gelen `DllMain`. Çıkmak için `DLLMain` işlev, dönüş `FALSE` gelen `DLL_PROCESS_ATTACH`.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|`exit`, `_Exit`, `_exit`|\<Process.h > veya \<stdlib.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_exit.c
// This program returns an exit code of 1. The
// error code could be tested in a batch file.

#include <stdlib.h>

int main( void )
{
   exit( 1 );
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)  
[abort](../../c-runtime-library/reference/abort.md)  
[atexit](../../c-runtime-library/reference/atexit.md)  
[_cexit, _c_exit](../../c-runtime-library/reference/cexit-c-exit.md)  
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)  
[_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)  
[quick_exit](../../c-runtime-library/reference/quick-exit1.md)  
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)  
[system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)  
