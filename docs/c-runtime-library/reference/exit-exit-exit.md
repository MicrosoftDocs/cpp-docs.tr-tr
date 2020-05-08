---
title: exit, _Exit, _exit
ms.date: 4/2/2020
api_name:
- _exit
- exit
- _o__exit
- _o_exit
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: a1c0eeaa6d66e91b913ce7940d37409fc4f6ac29
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909671"
---
# <a name="exit-_exit-_exit"></a>exit, _Exit, _exit

Çağıran işlemi sonlandırır. **Exit** işlevi, temizlik sonrasında onu sonlandırır; **_exit** ve **_exit** hemen sonlandırın.

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

*durumlarına*<br/>
Çıkış durum kodu.

## <a name="remarks"></a>Açıklamalar

**Exit**, **_exit** ve **_exit** işlevleri çağıran işlemi sonlandırır. **Çıkış** işlevi, iş parçacığı yerel nesneleri için yıkıcıları çağırır, sonra (ilk kez çıkar (LIFO) sırada), bu, **atexit** ve **_onexit**tarafından kaydedilen işlevler ve işlemi bitirmeden önce tüm dosya arabelleğini temizler. **_Exit** ve **_exit** işlevleri, iş parçacığı yerel nesnelerini yok etmeden veya **atexit** veya **_onexit** işlevlerini işlemeden ve akış arabelleklerini temizlemeden işlemi sonlandırır.

**Çıkış**, **_exit** ve **_exit** çağrıları bir değer döndürmese de, *durum* değeri ana bilgisayar ortamında kullanılabilir hale getirilir veya bir varsa, işlem çıktıktan sonra işlemi çağırma işlemini bekliyor. Genellikle, çağıran bir hata belirtmek için normal bir çıkış veya başka bir değer belirtmek üzere *durum* değerini 0 olarak ayarlar. *Durum* değeri, işletim sistemi Batch komutu **ERRORLEVEL** tarafından kullanılabilir ve iki sabitden biri ile temsil edilir: 0 değerini temsil eden **EXIT_SUCCESS**, 1 değerini temsil eden **EXIT_FAILURE**.

**Çıkış**, **_exit**, **_exit**, **quick_exit**, **_cexit**ve **_c_exit** işlevleri aşağıdaki gibi davranır.

|İşlev|Açıklama|
|--------------|-----------------|
|**çıkıp**|Tüm C Kitaplığı sonlandırma yordamlarını gerçekleştirir, işlemi sonlandırır ve konak ortamına sağlanan durum kodunu sağlar.|
|**_Exit**|En az C Kitaplığı sonlandırma yordamlarını gerçekleştirir, işlemi sonlandırır ve konak ortamına sağlanan durum kodunu sağlar.|
|**_exit**|En az C Kitaplığı sonlandırma yordamlarını gerçekleştirir, işlemi sonlandırır ve konak ortamına sağlanan durum kodunu sağlar.|
|**quick_exit**|Hızlı C Kitaplığı sonlandırma yordamlarını gerçekleştirir, işlemi sonlandırır ve konak ortamına sağlanan durum kodunu sağlar.|
|**_cexit**|Tüm C Kitaplığı sonlandırma yordamlarını gerçekleştirir ve çağırana döner. İşlemi sonlandırır.|
|**_c_exit**|En az C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana döner. İşlemi sonlandırır.|

**Exit**, **_exit** veya **_exit** işlevini çağırdığınızda, çağrı sırasında mevcut olan geçici veya otomatik nesnelerin yıkıcıları çağrılmaz. Bir otomatik nesne, bir işlevde tanımlanan statik olmayan bir yerel nesnedir. Geçici bir nesne, bir işlev çağrısının döndürdüğü değer gibi derleyici tarafından oluşturulan bir nesnedir. **Exit**, **_exit**veya **_exit**çağrısından önce otomatik bir nesneyi yok etmek için, burada gösterildiği gibi, nesne için yok ediciyi açıkça çağırın:

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

**DllMain**'den **çıkış** çağırmak için **DLL_PROCESS_ATTACH** kullanmayın. **DllMain** işlevinden çıkmak için **DLL_PROCESS_ATTACH**'den **false** döndürün.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**Çıkış**, **_exit** **_exit**|\<Process. h> veya \<Stdlib. h>|

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
[durdurulmaya](abort.md)<br/>
[atexit](atexit.md)<br/>
[_cexit, _c_exit](cexit-c-exit.md)<br/>
[_exec, _wexec Işlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[quick_exit](quick-exit1.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
