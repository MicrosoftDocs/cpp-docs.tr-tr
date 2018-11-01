---
title: _malloca
ms.date: 11/04/2016
apiname:
- _malloca
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
apitype: DLLExport
f1_keywords:
- malloca
- _malloca
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
ms.openlocfilehash: 8c8ce8bdf8ab40cae45ecec9c4b182bdf3d6bc82
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563988"
---
# <a name="malloca"></a>_malloca

Yığında bellek ayırır. Bu bir sürümüdür [_alloca](alloca.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
void *_malloca(
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
Yığından ayrılacak bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

**_Malloca** rutin döndürür bir **void** nesnenin herhangi bir türde bir depolama için uygun şekilde hizalanması garanti ayrılan alanı işaretçisi. Varsa *boyutu* 0 ' dır **_malloca** sıfır uzunluklu öğeyi ayırır ve bu öğeye geçerli bir işaretçi döndürür.

Alanı ayırdığınızda, bir yığın taşması özel durumu oluşturulur. Yığın taşması özel durumu bir C++ özel durum değil; Bu, yapılandırılmış bir özel durumdur. C++ özel durum işleme kullanmak yerine, kullanmanız gerekir [yapılandırılmış özel durum işleme](../../cpp/structured-exception-handling-c-cpp.md) (SEH).

## <a name="remarks"></a>Açıklamalar

**_malloca** ayırır *boyutu* bayt program yığınına veya belirli bir boyuta tarafından verilen bayt cinsinden istek aşarsa, yığın **_ALLOCA_S_THRESHOLD**. Arasındaki fark **_malloca** ve **_alloca** olan **_alloca** yığında boyutundan bağımsız olarak her zaman ayırır. Farklı **_alloca**, hangi gerektirmez veya buna izin vermek için bir çağrı **ücretsiz** ayrılmış şekilde, belleği boşaltmak için **_malloca** gerektirir [_freea](freea.md)belleği boşaltmak için. Hata ayıklama modunda **_malloca** her zaman yığından belleği ayırır.

Açıkça çağırmak için kısıtlamalar **_malloca** bir özel durum işleyicisi (EH). X86 sınıfı işlemciler üzerinde çalışan EH düzenleri kendi bellek çerçevede çalışmak: yığın işaretçisi kapsayan işlevin geçerli konumuna bağlı olmayan bellek alanında gerçekleştirdikleri görevleri. En yaygın olarak görülen uygulamalar, Windows NT yapılandırılmış özel durum işleme (SEH) ve C++ catch yan tümcesi ifadeleri içerir. Bu nedenle, açıkça çağırma **_malloca** herhangi birinde çağıran EH yordam için dönüş sırasında program hata aşağıdaki senaryolarda sonuçları:

- Windows NT SEH özel durum filtre ifadesinin: **__except** (`_malloca ()` )

- Windows NT SEH son özel durum işleyicisi: **__finally** {`_malloca ()` }

- C++ EH catch yan tümcesinin ifadesi

Ancak, **_malloca** doğrudan EH yordam içinde ya da çağrılan bir uygulama tarafından sağlanan bir geri çağırma daha önce listelenen EH senaryoları biri tarafından çağrılabilir.

> [!IMPORTANT]
> Windows XP'de, **_malloca** çağrılır bir try/catch bloğu içinde çağırmalısınız [_resetstkoflw](resetstkoflw.md) catch bloğu içinde.

Yukarıdaki sınırlamalara kullanırken, ek olarak [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) seçeneği **_malloca** kullanılamaz **__except** engeller. Daha fazla bilgi için [/CLR kısıtlamalar](../../build/reference/clr-restrictions.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_malloca**|\<malloc.h >|

## <a name="example"></a>Örnek

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

## <a name="example"></a>Örnek

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

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_resetstkoflw](resetstkoflw.md)<br/>
