---
title: _aligned_malloc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_malloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _aligned_malloc
- alligned_malloc
dev_langs:
- C++
helpviewer_keywords:
- aligned_malloc function
- _aligned_malloc function
ms.assetid: fb788d40-ee94-4039-aa4d-97d73dab1ca0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b500471a3580af9045f1c42707a543669da48c7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063183"
---
# <a name="alignedmalloc"></a>_aligned_malloc

Belirtilen hizalama sınırındaki belleği ayırır.

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_malloc(
    size_t size,
    size_t alignment
);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
İstenen bellek ayırmasının boyutu.

*Hizalama*<br/>
Hizalama değeri 2'in tam sayı üssü olması gerekir.

## <a name="return-value"></a>Dönüş Değeri

Ayrılan bellek bloğuna işaretçi veya işlem başarısız olursa NULL. İşaretçi katı *hizalama*.

## <a name="remarks"></a>Açıklamalar

**_aligned_malloc** dayanır [malloc](malloc.md).

**_aligned_malloc** işaretlenmiş `__declspec(noalias)` ve `__declspec(restrict)`, işlevin genel değişkenleri sağlanır ve diğer ad verilmediğini göstermeyecektir işaretçi döndüren anlamına gelir. Daha fazla bilgi için [noalias](../../cpp/noalias.md) ve [kısıtlama](../../cpp/restrict.md).

Bu işlev ayarlar `errno` için `ENOMEM` bellek ayırma başarısız olursa veya istenen boyutu büyüktür `_HEAP_MAXREQ`. Hakkında daha fazla bilgi için `errno`, bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_malloc** kendi parametrelerini doğrular. Varsa *hizalama* 2'in kuvveti değil veya *boyutu* sıfırsa bu işlev içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Devam etmek için bu işlev dönüşleri NULL ve kümeleri yürütülmesine izin veriliyorsa `errno` için `EINVAL`.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_malloc**|\<malloc.h >|

## <a name="example"></a>Örnek

```C
// crt_aligned_malloc.c

#include <malloc.h>
#include <stdio.h>

int main() {
    void    *ptr;
    size_t  alignment,
            off_set;

    // Note alignment should be 2^N where N is any positive int.
    alignment = 16;
    off_set = 5;

    // Using _aligned_malloc
    ptr = _aligned_malloc(100, alignment);
    if (ptr == NULL)
    {
        printf_s( "Error allocation aligned memory.");
        return -1;
    }
    if (((unsigned long long)ptr % alignment ) == 0)
        printf_s( "This pointer, %p, is aligned on %zu\n",
                  ptr, alignment);
    else
        printf_s( "This pointer, %p, is not aligned on %zu\n",
                  ptr, alignment);

    // Using _aligned_realloc
    ptr = _aligned_realloc(ptr, 200, alignment);
    if ( ((unsigned long long)ptr % alignment ) == 0)
        printf_s( "This pointer, %p, is aligned on %zu\n",
                  ptr, alignment);
    else
        printf_s( "This pointer, %p, is not aligned on %zu\n",
                  ptr, alignment);
    _aligned_free(ptr);

    // Using _aligned_offset_malloc
    ptr = _aligned_offset_malloc(200, alignment, off_set);
    if (ptr == NULL)
    {
        printf_s( "Error allocation aligned offset memory.");
        return -1;
    }
    if ( ( (((unsigned long long)ptr) + off_set) % alignment ) == 0)
        printf_s( "This pointer, %p, is offset by %zu on alignment of %zu\n",
                  ptr, off_set, alignment);
    else
        printf_s( "This pointer, %p, does not satisfy offset %zu "
                  "and alignment %zu\n",ptr, off_set, alignment);

    // Using _aligned_offset_realloc
    ptr = _aligned_offset_realloc(ptr, 200, alignment, off_set);
    if (ptr == NULL)
    {
        printf_s( "Error reallocation aligned offset memory.");
        return -1;
    }
    if ( ( (((unsigned long long)ptr) + off_set) % alignment ) == 0)
        printf_s( "This pointer, %p, is offset by %zu on alignment of %zu\n",
                  ptr, off_set, alignment);
    else
        printf_s( "This pointer, %p, does not satisfy offset %zu and "
                  "alignment %zu\n", ptr, off_set, alignment);

    // Note that _aligned_free works for both _aligned_malloc
    // and _aligned_offset_malloc. Using free is illegal.
    _aligned_free(ptr);
}
```

```Output
This pointer, 3280880, is aligned on 16
This pointer, 3280880, is aligned on 16
This pointer, 3280891, is offset by 5 on alignment of 16
This pointer, 3280891, is offset by 5 on alignment of 16
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)