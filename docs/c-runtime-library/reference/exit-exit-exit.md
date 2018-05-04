---
title: Çıkış, _Exit, _exit | Microsoft Docs
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb62c18f7508a21e24fb5628e8ac01162db1405e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="exit-exit-exit"></a>Çıkış, _Exit, _exit

Arama işlemi sonlandırır. **Çıkmak** işlevi sonlandırır, temizleme sonrasında; **_exit** ve **_Exit** hemen sonlandır.

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

*Durum* çıkış durum kodu.

## <a name="remarks"></a>Açıklamalar

**Çıkmak**, **_Exit** ve **_exit** işlevleri çağırma işlemi sonlandırılacak. **Çıkmak** işlevi çağırır Yıkıcılar iş parçacığı yerel nesneler için daha sonra çağırır — son olarak ilk çıkar (LIFO) sırayla — tarafından kaydedilen işlevleri **atexit** ve **_onexit**ve işlem sona erdirmeden önce tüm dosya arabelleklerini alır. **_Exit** ve **_exit** işlevleri sonlandırma işlemi iş parçacığı yerel nesneleri yok etme veya işlemeden **atexit** veya **_onexit**işlevler ve akış arabellekleri temizleme olmadan.

Rağmen **çıkmak**, **_Exit** ve **_exit** çağrıları değer'de bir değer döndürmeyen *durum* konak ortamında kullanılabilir veya işlem çıktıktan sonra varsa, arama işlemi bekleniyor. Genellikle, çağıran kümeleri *durum* değer normal bir çıkış göstermek için 0 veya bir hata göstermek için başka bir değer. *Durum* değeri işletim sistemi toplu komutuna kullanılabilir **ERRORLEVEL** ve iki sabitlerden biri tarafından temsil edilen: **exıt_success**, bir değeri temsil eder 0 veya **exıt_faılure**, 1 değerini temsil eder.

**Çıkmak**, **_Exit**, **_exit**, **quick_exit**, **_cexit**, ve **_c_exit** işlevleri gibi davranır.

|İşlev|Açıklama|
|--------------|-----------------|
|**Çıkış**|Tam C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının için sağlanan durum kodu sağlar.|
|**_Exit**|En az C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının için sağlanan durum kodu sağlar.|
|**_exit**|En az C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının için sağlanan durum kodu sağlar.|
|**quick_exit**|Hızlı C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının için sağlanan durum kodu sağlar.|
|**_cexit**|Tam C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana döndürür. İşlemi Sonlandır değil.|
|**_c_exit**|En az C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana döndürür. İşlemi Sonlandır değil.|

Çağırdığınızda **çıkmak**, **_Exit** veya **_exit** işlev çağrısı sırada mevcut geçici veya otomatik nesneleri için Yıkıcılar çağrılır değil. Tanımlı bir işlevde statik olmayan yerel bir nesne bir otomatik nesnesidir. Geçici bir nesne gibi bir işlev çağrısı tarafından döndürülen değer derleyici tarafından oluşturulan nesnedir. Arama yapmadan önce bir otomatik nesne yok etmek için **çıkmak**, **_Exit**, veya **_exit**, açıkça yıkıcı nesne için aşağıda gösterildiği gibi çağırın:

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

Kullanmayın **DLL_PROCESS_ATTACH** çağırmak için **çıkmak** gelen **DllMain**. Çıkmak için **DLLMain** işlev, dönüş **FALSE** gelen **DLL_PROCESS_ATTACH**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**Çıkış**, **_Exit**, **_exit**|\<Process.h > veya \<stdlib.h >|

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

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_cexit, _c_exit](cexit-c-exit.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[quick_exit](quick-exit1.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
