---
description: 'Hakkında daha fazla bilgi edinin: _malloca'
title: _malloca
ms.date: 11/04/2016
api_name:
- _malloca
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- malloca
- _malloca
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
ms.openlocfilehash: 8357bc15ba432a0adb390494882ee4b63adf70f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299806"
---
# <a name="_malloca"></a>_malloca

Yığında bellek ayırır. Bu, [CRT 'Deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [_alloca](alloca.md) bir sürümüdür.

## <a name="syntax"></a>Sözdizimi

```C
void *_malloca(
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Yığından ayrılacak bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

**_Malloca** yordamı **`void`** , ayrılan alana bir işaretçi döndürür ve bu, herhangi bir nesne türünün depolanması için uygun şekilde hizalı olarak garanti edilir. *Boyut* 0 ise, **_malloca** sıfır uzunluklu bir öğe ayırır ve bu öğeye geçerli bir işaretçi döndürür.

*Boyut* **_ALLOCA_S_THRESHOLD** değerinden büyükse **_malloca** yığına ayırmaya çalışır ve alan ayrılamadığında null bir işaretçi döndürür. *Boyut* **_ALLOCA_S_THRESHOLD** küçüktür veya eşitse **_malloca** yığına ayrılmaya çalışır ve alan ayrılamadığında bir yığın taşması özel durumu oluşturulur. Yığın taşması özel durumu bir C++ özel durumu değil; Bu, yapılandırılmış bir özel durumdur. C++ özel durum işlemeyi kullanmak yerine, bu özel durumu yakalamak için [yapılandırılmış özel durum işleme](../../cpp/structured-exception-handling-c-cpp.md) (SEH) kullanmanız gerekir.

## <a name="remarks"></a>Açıklamalar

**_malloca** , istek **_ALLOCA_S_THRESHOLD** tarafından verilen bayt cinsinden belirli bir boyutu aşarsa program yığınından veya yığında *Boyut* baytları ayırır. **_Malloca** ve **_alloca** arasındaki fark, **_alloca** her zaman yığına ayrılan, boyuttan bağımsız olarak olur. _Alloca **farklı olarak,** ayrılan belleği serbest bırakmak için bir çağrı gerektirmeyen veya buna izin veren aksine, **_malloca** belleği boşaltmak için [_freea](freea.md) kullanılmasını gerektirir. Hata ayıklama modunda **_malloca** her zaman yığından bellek ayırır.

Özel durum işleyicisinde (EH) **_malloca** açıkça çağırmak için kısıtlamalar vardır. X86 sınıfı işlemcilerde çalışan EH yordamları kendi bellek çerçevesinde çalışır: kendi görevlerini, kapsayan işlevin yığın işaretçisinin geçerli konumuna bağlı olmayan bellek alanında gerçekleştirirler. En yaygın uygulamalar Windows NT yapılandırılmış özel durum işleme (SEH) ve C++ catch yan tümcesi ifadelerini içerir. Bu nedenle, aşağıdaki senaryolardan herhangi birinde **_malloca** açıkça çağırmak, çağıran Eh yordamına geri dönme sırasında program hatasına neden olur:

- Windows NT SEH özel durum filtresi ifadesi: **`__except`** ( `_malloca ()` )

- Windows NT SEH son özel durum işleyicisi: **`__finally`** { `_malloca ()` }

- C++ EH catch yan tümcesi ifadesi

Ancak, **_malloca** doğrudan bir Eh yordamının içinden veya daha önce listelenen eh senaryolarından biri tarafından çağrılan uygulama tarafından sağlanan geri aramadan çağrılabilir.

> [!IMPORTANT]
> Windows XP 'de, bir try/catch bloğu içinde **_malloca** çağrılırsa, catch bloğunda [_resetstkoflw](resetstkoflw.md) çağırmanız gerekir.

Yukarıdaki kısıtlamalara ek olarak, [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) seçeneği kullanılırken **_malloca** **`__except`** bloklarda kullanılamaz. Daha fazla bilgi için bkz. [/clr kısıtlamaları](../../build/reference/clr-restrictions.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_malloca**|\<malloc.h>|

## <a name="example-malloca"></a>Örnek: malloca

```C
// crt_malloca_simple.c
#include <stdio.h>
#include <malloc.h>

void Fn()
{
   char * buf = (char *)_malloca( 100 );
   // do something with buf
   _freea( buf );
}

int main()
{
   Fn();
}
```

## <a name="example-malloca-exception"></a>Örnek: malloca özel durumu

```C
// crt_malloca_exception.c
// This program demonstrates the use of
// _malloca and trapping any exceptions
// that may occur.

#include <windows.h>
#include <stdio.h>
#include <malloc.h>

int main()
{
    int     size;
    int     numberRead = 0;
    int     errcode = 0;
    void    *p = NULL;
    void    *pMarker = NULL;

    while (numberRead == 0)
    {
        printf_s("Enter the number of bytes to allocate "
                 "using _malloca: ");
        numberRead = scanf_s("%d", &size);
    }

    // Do not use try/catch for _malloca,
    // use __try/__except, since _malloca throws
    // Structured Exceptions, not C++ exceptions.

    __try
    {
        if (size > 0)
        {
            p =  _malloca( size );
        }
        else
        {
            printf_s("Size must be a positive number.");
        }
        _freea( p );
    }

    // Catch any exceptions that may occur.
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )
    {
        printf_s("_malloca failed!\n");

        // If the stack overflows, use this function to restore.
        errcode = _resetstkoflw();
        if (errcode)
        {
            printf("Could not reset the stack!");
            _exit(1);
        }
    };
}
```

### <a name="input"></a>Giriş

```Input
1000
```

### <a name="sample-output"></a>Örnek Çıktı

```Output
Enter the number of bytes to allocate using _malloca: 1000
```

## <a name="see-also"></a>Ayrıca bkz.

[Bellek ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_resetstkoflw](resetstkoflw.md)<br/>
