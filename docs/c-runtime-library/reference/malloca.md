---
title: _malloca | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c6f6b731bce5667ca992e7181518bf0a9eb2b87
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403293"
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

**_Malloca** rutin döndürür bir **void** nesnesinin herhangi bir türde bir depolama için uygun hizalanacak garanti ayrılan alanı işaretçi. Varsa *boyutu* 0 ' dır **_malloca** sıfır uzunluklu öğesi ayırır ve geçerli bir işaretçi için bu öğeyi döndürür.

Bir yığın taşması özel durumu alanı ayrılamıyor ise oluşturulur. Yığın taşması özel durumu C++ özel durum değil; yapılandırılmış özel durum var. C++ özel durum işleme kullanmak yerine, kullanmalısınız [yapılandırılmış özel durum işleme](../../cpp/structured-exception-handling-c-cpp.md) (SEH).

## <a name="remarks"></a>Açıklamalar

**_malloca** ayırır *boyutu* program yığını ya da belirli bir boyuta tarafından verilen bayt cinsinden istek aşarsa, öbek bayt **_ALLOCA_S_THRESHOLD**. Arasındaki farkı **_malloca** ve **_alloca** olan **_alloca** yığında boyutuna bakılmaksızın her zaman ayırır. Aksine **_alloca**, hangi gerektirmez veya bir çağrısına izin **ücretsiz** şekilde ayrılmış, belleği boşaltmak için **_malloca** kullanılmasını gerektiren [_freea](freea.md)belleği boşaltmak için. Hata ayıklama modunda **_malloca** her zaman yığınından bellek ayırır.

Açıkça çağırmak için kısıtlamalar vardır **_malloca** bir özel durum işleyicisi (EH). X86 sınıfı işlemcilerde çalıştırmak EH yordamları çalışan kendi bellek çerçevede: yığın işaretçisi kapsayan işlevinin geçerli konumuna dayalı olmayan bellek alanında görevlerini gerçekleştirdikleri. En yaygın uygulamaları, Windows NT yapılandırılmış özel durum (SEH) işleme ve C++ catch yan tümcesi ifadeleri içerir. Bu nedenle, açıkça çağırma **_malloca** herhangi bir program hatası EH yordamı çağrılırken dönün sırasında aşağıdaki senaryoları sonuçlarında:

- Windows NT SEH özel durum filtre ifadesi: **__except** (`_malloca ()` )

- Windows NT SEH son özel durum işleyici: **__finally** {`_malloca ()` }

- C++ EH catch yan tümcesinin ifadesi

Ancak, **_malloca** doğrudan bir EH yordamı içinde veya çağrılan bir uygulama tarafından sağlanan bir geri çağırma senaryolardan biri, daha önce listelenen EH tarafından çağrılabilir.

> [!IMPORTANT]
> Windows XP'de, **_malloca** çağrılır try/catch bloğunun içine çağırmalısınız [_resetstkoflw](resetstkoflw.md) catch bloğu içinde.

Yukarıdaki kısıtlamaları kullanırken, ek olarak [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) seçeneği **_malloca** kullanılamaz **__except** engeller. Daha fazla bilgi için bkz: [/CLR kısıtlamalar](../../build/reference/clr-restrictions.md).

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
