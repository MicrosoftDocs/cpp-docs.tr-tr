---
title: exit, _Exit, _exit
ms.date: 01/02/2018
api_name:
- _exit
- exit
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: fd988ca6339c00b454d673d3bec6f137753ac83a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941664"
---
# <a name="exit-_exit-_exit"></a>exit, _Exit, _exit

Çağıran işlemi sonlandırır. **Exit** işlevi, temizlik sonrasında onu sonlandırır; **_çık** ve **_çıkış** hemen sonlandır.

> [!NOTE]
> Test veya hata ayıklama senaryoları dışında Evrensel Windows Platformu (UWP) uygulamasını kapatmak için bu yöntemi kullanmayın. Bir mağaza uygulamasını kapatmak için programlı veya Kullanıcı arabirimi yollarına [Microsoft Store ilkelerine](/legal/windows/agreements/store-policies)göre izin verilmez. Daha fazla bilgi için bkz. [UWP uygulama yaşam döngüsü](/windows/uwp/launch-resume/app-lifecycle). Windows 10 uygulamaları hakkında daha fazla bilgi için bkz. [Windows 10 uygulamaları Için nasıl yapılır kılavuzlarında](https://developer.microsoft.com/windows/apps).

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

*status*<br/>
Çıkış durum kodu.

## <a name="remarks"></a>Açıklamalar

**Çıkış**, **_exit** ve **_exit** işlevleri çağıran işlemi sonlandırır. **Çıkış** işlevi, iş parçacığı yerel nesneleri için yıkıcıları çağırır, sonra (ilk kez çıkar (LIFO) sırada), bir **atexit** ve **_onexit**tarafından kaydedilen işlevler ve sonra tüm dosya arabelleğini işle. **_Exit** ve **_exit** işlevleri, iş parçacığı yerel nesnelerini yok etmeden veya **atexit** ya da **_onexit** işlevlerini işlemeden ve akış arabelleklerini temizlemeye gerek kalmadan işlemi sonlandırır.

**Çıkış**, **_çıkış** ve **_çıkış** çağrıları bir değer döndürmese de, *durum* değeri ana bilgisayar ortamında kullanılabilir hale getirilir veya bir varsa, işlem çıktıktan sonra işlemi çağırma işlemini bekliyor. Genellikle, çağıran bir hata belirtmek için normal bir çıkış veya başka bir değer belirtmek üzere *durum* değerini 0 olarak ayarlar. *Durum* değeri, işletim sistemi Batch komutu **ERRORLEVEL** tarafından kullanılabilir ve iki sabitden biri tarafından temsil edilir: 0 değerini temsil eden **EXIT_SUCCESS**, 1 değerini temsil eden **EXIT_FAILURE**.

**Çıkış**, **_exit**, **_exit**, **quick_exit**, **_cexit**ve **_c_exit** işlevleri aşağıdaki gibi davranır.

|İşlev|Açıklama|
|--------------|-----------------|
|**çıkıp**|Tüm C Kitaplığı sonlandırma yordamlarını gerçekleştirir, işlemi sonlandırır ve konak ortamına sağlanan durum kodunu sağlar.|
|**_Çıkış**|En az C Kitaplığı sonlandırma yordamlarını gerçekleştirir, işlemi sonlandırır ve konak ortamına sağlanan durum kodunu sağlar.|
|**_çıkış**|En az C Kitaplığı sonlandırma yordamlarını gerçekleştirir, işlemi sonlandırır ve konak ortamına sağlanan durum kodunu sağlar.|
|**quick_exit**|Hızlı C Kitaplığı sonlandırma yordamlarını gerçekleştirir, işlemi sonlandırır ve konak ortamına sağlanan durum kodunu sağlar.|
|**_cexit**|Tüm C Kitaplığı sonlandırma yordamlarını gerçekleştirir ve çağırana döner. İşlemi sonlandırır.|
|**_c_exit**|En az C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana döner. İşlemi sonlandırır.|

**Çıkış**, **_exit** veya **_exit** işlevini çağırdığınızda, çağrı sırasında mevcut olan geçici veya otomatik nesnelerin yıkıcıları çağrılmaz. Bir otomatik nesne, bir işlevde tanımlanan statik olmayan bir yerel nesnedir. Geçici bir nesne, bir işlev çağrısının döndürdüğü değer gibi derleyici tarafından oluşturulan bir nesnedir. **Çıkış**, **_exit**veya **_exit**çağrısı yapmadan önce otomatik bir nesneyi yok etmek için, burada gösterildiği gibi, nesne için yok ediciyi açıkça çağırın:

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

**DllMain**'den **Çıkış** çağırmak için **DLL_PROCESS_ATTACH** kullanmayın. **DllMain** işlevinden çıkmak için **DLL_PROCESS_ATTACH**adresinden **false** döndürün.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**Çıkış**, **_çıkış**, **_çıkış**|\<Process. h > veya \<Stdlib. h >|

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
