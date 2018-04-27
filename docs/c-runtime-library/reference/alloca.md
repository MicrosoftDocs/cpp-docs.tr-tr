---
title: _alloca | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 27ee6e3c63a086ad2371350baddd038a93f36794
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="alloca"></a>_alloca

Yığında bellek ayırır. Daha güvenli bir sürümü olmadığından bu işlev kullanım dışıdır; bkz: [_malloca](malloca.md).

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

**_Alloca** rutin döndürür bir **void** nesnesinin herhangi bir türde bir depolama için uygun hizalanacak garanti ayrılan alanı işaretçi. Varsa *boyutu* 0 ' dır **_alloca** sıfır uzunluklu öğesi ayırır ve geçerli bir işaretçi için bu öğeyi döndürür.

Bir yığın taşması özel durumu alanı ayrılamıyor ise oluşturulur. Yığın taşması özel durumu C++ özel durum değil; yapılandırılmış özel durum var. C++ özel durum işleme kullanmak yerine, kullanmalısınız [yapılandırılmış özel durum işleme](../../cpp/structured-exception-handling-c-cpp.md) (SEH).

## <a name="remarks"></a>Açıklamalar

**_alloca** ayırır *boyutu* program yığından bayt. (Ayırma yalnızca kapsamının dışına değil geçtiğinde) çağıran işlevi çıktığında ayrılan alanı boşaltılır. Bu nedenle, tarafından döndürülen işaretçi değer geçmeyin **_alloca** bağımsız değişken olarak [ücretsiz](free.md).

Açıkça çağırmak için kısıtlamalar vardır **_alloca** bir özel durum işleyicisi (EH). X86 sınıfı işlemcilerde çalıştırmak EH yordamları çalışan kendi bellek çerçevede: yığın işaretçisi kapsayan işlevinin geçerli konumuna dayalı olmayan bellek alanında görevlerini gerçekleştirdikleri. En yaygın uygulamaları, Windows NT yapılandırılmış özel durum (SEH) işleme ve C++ catch yan tümcesi ifadeleri içerir. Bu nedenle, açıkça çağırma **_alloca** herhangi bir program hatası EH yordamı çağrılırken dönün sırasında aşağıdaki senaryoları sonuçlarında:

- Windows NT SEH özel durum filtre ifadesi: `__except ( _alloca() )`

- Windows NT SEH son özel durum işleyici: `__finally { _alloca() }`

- C++ EH catch yan tümcesinin ifadesi

Ancak, **_alloca** doğrudan bir EH yordamı içinde veya çağrılan bir uygulama tarafından sağlanan bir geri çağırma senaryolardan biri, daha önce listelenen EH tarafından çağrılabilir.

> [!IMPORTANT]
> Windows XP'de, **_alloca** çağrılır try/catch bloğunun içine çağırmalısınız [_resetstkoflw](resetstkoflw.md) catch bloğu içinde.

Yukarıdaki kısıtlamaları kullanırken, ek olarak[/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) seçeneği **_alloca** kullanılamaz **__except** engeller. Daha fazla bilgi için bkz: [/CLR kısıtlamalar](../../build/reference/clr-restrictions.md).

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
