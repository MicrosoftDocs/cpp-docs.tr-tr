---
title: _swab | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1ab841400bd002595508806797a9a204415b5f15
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
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

*src* kopyalanır ve takas için veri.

*Hedef* değiştirilen verileri için depolama konumu.

*n* kopyalanır ve takas bayt sayısı.

## <a name="return-value"></a>Dönüş değeri

**Swab** işlevi bir değer döndürmez. İşlev kümeleri **errno** için **EINVAL** her iki *src* veya *taşınmaya* işaretçidir null veya *n* küçük sıfır ve geçersiz bir parametre işleyici, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer dönüş kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

Varsa *n* olsa bile, **_swab** işlev kopyaları *n* baytlar *src*her çifti bitişik bayt değiştirir ve sonucundadepolar*taşınmaya*. Varsa *n* tek, olup **_swab** kopyalar ve ilk değiştirir *n*-1 bayt *src*, ve son bayt kopyalanmaz. **_Swab** işlevi farklı bayt sırası kullanan bir makine aktarmak için ikili verileri hazırlamak için genellikle kullanılır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_swab**|C: \<stdlib.h > C++: \<cstdlib > veya \<stdlib.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
