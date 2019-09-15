---
title: _alloca
ms.date: 11/04/2016
api_name:
- _alloca
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
- _alloca
- alloca
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
ms.openlocfilehash: 2212f9e40c78932b63eebfc221ad2f07fa3d3f9d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943706"
---
# <a name="_alloca"></a>_alloca

Yığında bellek ayırır. Daha güvenli bir sürüm kullanılabilir olduğundan bu işlev kullanım dışıdır; bkz. [_malloca](malloca.md).

## <a name="syntax"></a>Sözdizimi

```C
void *_alloca(
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Yığından ayrılacak bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

**_Alloca** yordamı, ayrılan alana **geçersiz** bir işaretçi döndürür. Bu, herhangi bir tür nesnenin depolanması için uygun şekilde hizalı olarak garanti edilir. *Boyut* 0 ise, **_alloca** sıfır uzunluklu bir öğe ayırır ve bu öğeye geçerli bir işaretçi döndürür.

Boşluk ayrılabileceği takdirde bir yığın taşması özel durumu oluşturulur. Yığın taşması özel durumu bir C++ özel durum değil; Bu, yapılandırılmış bir özel durumdur. Özel durum işlemenin C++ kullanılması yerine, [yapılandırılmış özel durum işleme](../../cpp/structured-exception-handling-c-cpp.md) (SEH) kullanmanız gerekir.

## <a name="remarks"></a>Açıklamalar

**_alloca** , program yığınından *Boyut* baytlarını ayırır. Ayrılan alan, çağırma işlevi çıktığında (ayırma yalnızca kapsam dışına çıktığında değil) otomatik olarak serbest bırakılır. Bu nedenle, **_alloca** tarafından döndürülen işaretçi değerini [boş](free.md)bir bağımsız değişken olarak geçirmeyin.

Özel durum işleyicisinde (EH) **_alloca 'yı** açıkça çağırmaya yönelik kısıtlamalar vardır. X86 sınıfı işlemcilerde çalışan EH yordamları kendi bellek çerçevesinde çalışır: Görevleri kapsayan işlevin yığın işaretçisinin geçerli konumuna bağlı olmayan bellek alanında gerçekleştirir. En yaygın uygulamalar Windows NT yapılandırılmış özel durum işleme (SEH) ve C++ catch yan tümcesi ifadelerini içerir. Bu nedenle, aşağıdaki senaryolardan herhangi birinde açıkça **_alloca 'yı** çağırmak, çağıran Eh yordamına geri dönme sırasında program hatasına neden olur:

- Windows NT SEH özel durum filtresi ifadesi:`__except ( _alloca() )`

- Windows NT SEH son özel durum işleyicisi:`__finally { _alloca() }`

- C++EH catch yan tümcesi ifadesi

Ancak, **_alloca** doğrudan bir Eh yordamının içinden veya daha önce listelenen eh senaryolarından biri tarafından çağrılan uygulama tarafından sağlanan geri aramadan çağrılabilir.

> [!IMPORTANT]
> Windows XP 'de, **_alloca** bir try/catch bloğu içinde çağrılırsa, catch bloğunda [_resetstkoflw](resetstkoflw.md) çağrısı yapmanız gerekir.

Yukarıdaki kısıtlamalara ek olarak,[/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) seçeneği kullanılırken, **_alloca** **__except** blokları içinde kullanılamaz. Daha fazla bilgi için bkz. [/clr kısıtlamaları](../../build/reference/clr-restrictions.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_alloca**|\<malloc. h >|

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
