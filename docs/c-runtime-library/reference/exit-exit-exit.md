---
title: Çıkış, _Exit, _exit
ms.date: 1/02/2018
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
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
ms.openlocfilehash: 7b2a22649d779f382bb4055b1e44c14312627ccd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451759"
---
# <a name="exit-exit-exit"></a>Çıkış, _Exit, _exit

Çağırma işlemi sonlandırır. **Çıkmak** işlevi, sonra temizleme; sonlandırır **_exit** ve **_Exit** hemen sonlandırın.

> [!NOTE]
> Bu yöntem, test veya hata ayıklama senaryoları dışında bir evrensel Windows Platformu (UWP) uygulamasını kapatmak için kullanmayın. Bir Store uygulamasını kapatmak için programlama veya UI yollarına göre izin verilmez [Microsoft Store ilkeleri](/legal/windows/agreements/store-policies). Daha fazla bilgi için [UWP uygulaması yaşam döngüsü](/windows/uwp/launch-resume/app-lifecycle). Windows 10 uygulamaları hakkında daha fazla bilgi için bkz: [nasıl yapılır kılavuzları için Windows 10 uygulamaları](https://developer.microsoft.com/windows/apps).

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

*Durumu*<br/>
Durum kodu çıkın.

## <a name="remarks"></a>Açıklamalar

**Çıkmak**, **_Exit** ve **_exit** işlevleri çağırma işlemi sonlandırın. **Çıkmak** işlevi yok ediciler çağırır için iş parçacığı-yerel nesneleri, sonra çağıran — son-giren ilk çıkar (LIFO) sırayla — tarafından kaydedilen işlevleri **atexit** ve **_onexit**ve işlem sonlandırılmadan önce tüm dosya arabelleklerini ardından alır. **_Exit** ve **_exit** işlevleri sonlandırma işlemi iş parçacığı-yerel nesneleri yok etme veya işleme **atexit** veya **_onexit**işlevler ve akış arabellekleri temizleme olmadan.

Ancak **çıkmak**, **_Exit** ve **_exit** çağrıları, bir değer, değer döndürmeyen *durumu* konak ortamı için kullanılabilir hale getirileceğini veya süreç bittikten sonra varsa, çağırma işlemi bekleniyor. Genellikle, arayanın kümeleri *durumu* değer normal bir çıkış göstermek için 0 ya da bir hatayı göstermek için başka bir değer. *Durumu* değeri işletim sistemi batch komutuna kullanılabilir **ERRORLEVEL** ve iki sabitlerinden birini tarafından temsil edilir: **exıt_success**, bir değeri temsil eder 0 veya **exıt_faılure**, 1 değerini temsil eder.

**Çıkmak**, **_Exit**, **_exit**, **quick_exit**, **_cexit**, ve **_c_exit** işlevler gibi davranır.

|İşlev|Açıklama|
|--------------|-----------------|
|**Çıkış**|Tam C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının sağlanan durum koduna sağlar.|
|**_Exit**|En az C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının sağlanan durum koduna sağlar.|
|**_exit**|En az C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının sağlanan durum koduna sağlar.|
|**quick_exit**|Hızlı C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının sağlanan durum koduna sağlar.|
|**_cexit**|Tam C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana döner. İşlemi Sonlandır değil.|
|**_c_exit**|En az C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana döner. İşlemi Sonlandır değil.|

Çağırdığınızda **çıkmak**, **_Exit** veya **_exit** işlevi çağrısı sırada mevcut geçici veya otomatik nesneler için yok ediciler değil çağrılır. Bir işlev içinde tanımlanmış statik olmayan bir yerel nesne bir otomatik nesnedir. Geçici bir nesne bir işlev çağrısı tarafından döndürülen bir değer gibi derleyici tarafından oluşturulan bir nesnedir. Çağırmadan önce otomatik nesneyi yok etmek **çıkmak**, **_Exit**, veya **_exit**, açıkça yıkıcı nesne için burada gösterildiği gibi çağırın:

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

Kullanmayın **DLL_PROCESS_ATTACH** çağrılacak **çıkmak** gelen **DllMain**. Çıkmak için **DLLMain** işlevi, iade **FALSE** gelen **DLL_PROCESS_ATTACH**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**Çıkış**, **_Exit**, **_exit**|\<Process.h > veya \<stdlib.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
