---
title: _alloca
ms.date: 11/04/2016
apiname:
- _alloca
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
- _alloca
- alloca
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
ms.openlocfilehash: 7c083e791301d3224709a5fc6c711ceaa6397d38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341606"
---
# <a name="alloca"></a>_alloca

Yığında bellek ayırır. Daha güvenli bir sürümü kullanılabilir olmadığından, bu işlev kullanım dışı; bkz: [_malloca](malloca.md).

## <a name="syntax"></a>Sözdizimi

```C
void *_alloca(
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
Yığından ayrılacak bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

**_Alloca** rutin döndürür bir **void** nesnenin herhangi bir türde bir depolama için uygun şekilde hizalanması garanti ayrılan alanı işaretçisi. Varsa *boyutu* 0 ' dır **_alloca** sıfır uzunluklu öğeyi ayırır ve bu öğeye geçerli bir işaretçi döndürür.

Alanı ayırdığınızda, bir yığın taşması özel durumu oluşturulur. Yığın taşması özel durumu bir C++ özel durum değil; Bu, yapılandırılmış bir özel durumdur. C++ özel durum işleme kullanmak yerine, kullanmanız gerekir [yapılandırılmış özel durum işleme](../../cpp/structured-exception-handling-c-cpp.md) (SEH).

## <a name="remarks"></a>Açıklamalar

**_alloca** ayırır *boyutu* program yığınına gelen baytlar. (Ayırma yalnızca kapsam dışına değil geçtiğinde) çağıran işlevin çıktığında ayrılan alanı otomatik olarak serbest bırakılır. Bu nedenle, tarafından döndürülen işaretçi değer geçmeyin **_alloca** bağımsız değişkeni olarak [ücretsiz](free.md).

Açıkça çağırmak için kısıtlamalar **_alloca** bir özel durum işleyicisi (EH). Kendi bellek çerçevede x86 sınıfı işlemciler üzerinde çalışan EH düzenleri çalışır: Kapsayan işlevin yığın işaretçisi geçerli konumuna bağlı olmayan bellek alanı bunlar görevlerini gerçekleştirin. En yaygın olarak görülen uygulamalar, Windows NT yapılandırılmış özel durum işleme (SEH) ve C++ catch yan tümcesi ifadeleri içerir. Bu nedenle, açıkça çağırma **_alloca** herhangi birinde çağıran EH yordam için dönüş sırasında program hata aşağıdaki senaryolarda sonuçları:

- Windows NT SEH özel durum filtre ifadesi: `__except ( _alloca() )`

- Windows NT SEH son özel durum işleyicisi: `__finally { _alloca() }`

- C++ EH catch yan tümcesinin ifadesi

Ancak, **_alloca** doğrudan EH yordam içinde ya da çağrılan bir uygulama tarafından sağlanan bir geri çağırma daha önce listelenen EH senaryoları biri tarafından çağrılabilir.

> [!IMPORTANT]
> Windows XP'de, **_alloca** çağrılır bir try/catch bloğu içinde çağırmalısınız [_resetstkoflw](resetstkoflw.md) catch bloğu içinde.

Yukarıdaki sınırlamalara kullanırken, ek olarak[/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) seçeneği **_alloca** kullanılamaz **__except** engeller. Daha fazla bilgi için [/CLR kısıtlamalar](../../build/reference/clr-restrictions.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_alloca**|\<malloc.h >|

## <a name="example"></a>Örnek

```C
// crt_alloca.c
// This program demonstrates the use of
// _alloca and trapping any exceptions
// that may occur.

#include <windows.h>
#include <stdio.h>
#include <malloc.h>

int main()
{
    int     size = 1000;
    int     errcode = 0;
    void    *pData = NULL;

    // Note: Do not use try/catch for _alloca,
    // use __try/__except, since _alloca throws
    // Structured Exceptions, not C++ exceptions.

    __try {
        // An unbounded _alloca can easily result in a
        // stack overflow.
        // Checking for a size < 1024 bytes is recommended.
        if (size > 0 && size < 1024)
        {
            pData = _alloca( size );
            printf_s( "Allocated %d bytes of stack at 0x%p",
                      size, pData);
        }
        else
        {
            printf_s("Tried to allocate too many bytes.\n");
        }
    }

    // If an exception occured with the _alloca function
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )
    {
        printf_s("_alloca failed!\n");

        // If the stack overflows, use this function to restore.
        errcode = _resetstkoflw();
        if (errcode)
        {
            printf_s("Could not reset the stack!\n");
            _exit(1);
        }
    };
}
```

```Output
Allocated 1000 bytes of stack at 0x0012FB50
```

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_resetstkoflw](resetstkoflw.md)<br/>
[_malloca](malloca.md)<br/>
