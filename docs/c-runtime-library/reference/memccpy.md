---
title: _memccpy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _memccpy
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _memccpy
dev_langs:
- C++
helpviewer_keywords:
- _memccpy function
- memccpy function
ms.assetid: 9a2337df-6e85-4eba-b247-dd0532f45ddb
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 661f148e1af0877d0e961d743272de84c485ff32
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="memccpy"></a>_memccpy

Arabellek karakterlerinden kopyalar.

## <a name="syntax"></a>Sözdizimi

```C
void *_memccpy(
   void *dest,
   const void *src,
   int c,
   size_t count
);
```

### <a name="parameters"></a>Parametreler

*Hedef*<br/>
Hedef işaretçi.

*src*<br/>
İşaretçi kaynağı.

*c*<br/>
Kopyalamak için son karakter.

*Sayısı*<br/>
Karakter sayısı.

## <a name="return-value"></a>Dönüş Değeri

Varsa karakter *c* kopyalanır, **_memccpy** işaretçisi karakteri döndürür *taşınmaya* , hemen karakter izler. Varsa *c* , döndürdüğü kopyalanmaz **NULL**.

## <a name="remarks"></a>Açıklamalar

**_Memccpy** işlevi kopyalar, 0 veya daha fazla karakter *src* için *taşınmaya*, ne zaman durdurma karakter *c* kopyalandı veya ne zaman *sayısı* karakterleri kopyalanır, ilk hangisi gelir.

**Güvenlik Notu** boyutu veya daha büyük kaynak arabelleği hedef arabelleği aynı olduğundan emin olun. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_memccpy**|\<Memory.h > veya \<string.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_memccpy.c

#include <memory.h>
#include <stdio.h>
#include <string.h>

char string1[60] = "The quick brown dog jumps over the lazy fox";

int main( void )
{
   char buffer[61];
   char *pdest;

   printf( "Function: _memccpy 60 characters or to character 's'\n" );
   printf( "Source: %s\n", string1 );
   pdest = _memccpy( buffer, string1, 's', 60 );
   *pdest = '\0';
   printf( "Result: %s\n", buffer );
   printf( "Length: %d characters\n", strlen( buffer ) );
}
```

### <a name="output"></a>Çıkış

```Output
Function: _memccpy 60 characters or to character 's'
Source: The quick brown dog jumps over the lazy fox
Result: The quick brown dog jumps
Length: 25 characters
```

## <a name="see-also"></a>Ayrıca bkz.

[Ara Bellek Düzenlemesi](../../c-runtime-library/buffer-manipulation.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
