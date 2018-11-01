---
title: _swab
ms.date: 11/04/2016
apiname:
- _swab
- stdlib/_swab
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _swab
- stdlib/_swab
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
ms.openlocfilehash: 64753383bcb94947e6b413b5f55ac6e2d9c7dbca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603040"
---
# <a name="swab"></a>_swab

Bayt değiştirir.

## <a name="syntax"></a>Sözdizimi

```C
void _swab(
   char *src,
   char *dest,
   int n
);
```

## <a name="parameters"></a>Parametreler

*src*<br/>
Kopyalanır ve takas için veriler.

*Hedef*<br/>
Değiştirilen verileri için depolama konumu.

*n*<br/>
Kopyalanır ve takas için bayt sayısı.

## <a name="return-value"></a>Dönüş değeri

**Swab** işlevi, bir değer döndürmüyor. İşlev kümeleri **errno** için **EINVAL** ya da *src* veya *dest* işaretçisi, null veya *n* küçük sıfır ve geçersiz parametre açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md).

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer döndürme kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

Varsa *n* olsa bile, **_swab** işlev kopyaları *n* bayt *src*bitişik bayt her çiftini değiştirir ve sonucu konumundadepolar*dest*. Varsa *n* tektir, **_swab** kopyalar ve ilk değiştirir *n*-1 bayt *src*, ve son bayt kopyalanmaz. **_Swab** işlevi genellikle farklı bayt sırası kullanan bir bilgisayara aktarmak için ikili verileri hazırlamak için kullanılır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_swab**|C: \<stdlib.h > C++: \<cstdlib > veya \<stdlib.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_swab.c

#include <stdlib.h>
#include <stdio.h>

char from[] = "BADCFEHGJILKNMPORQTSVUXWZY";
char to[] =   "...........................";

int main()
{
    printf("Before: %s  %d bytes\n        %s\n\n", from, sizeof(from), to);
    _swab(from, to, sizeof(from));
    printf("After:  %s\n        %s\n\n", from, to);
}
```

```Output
Before: BADCFEHGJILKNMPORQTSVUXWZY  27 bytes
        ...........................

After:  BADCFEHGJILKNMPORQTSVUXWZY
        ABCDEFGHIJKLMNOPQRSTUVWXYZ.
```

## <a name="see-also"></a>Ayrıca bkz.

[Ara Bellek Düzenlemesi](../../c-runtime-library/buffer-manipulation.md)<br/>
