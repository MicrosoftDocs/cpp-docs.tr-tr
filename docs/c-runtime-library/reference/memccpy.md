---
title: _memccpy
ms.date: 11/04/2016
api_name:
- _memccpy
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
- api-ms-win-crt-string-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _memccpy
helpviewer_keywords:
- _memccpy function
- memccpy function
ms.assetid: 9a2337df-6e85-4eba-b247-dd0532f45ddb
ms.openlocfilehash: 097cefb504ffcdbfbe6bf131d5e8b1837d11a47a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951974"
---
# <a name="_memccpy"></a>_memccpy

Bir arabellekteki karakterleri kopyalar.

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

*HD*<br/>
Hedefe yönelik işaretçi.

*YN*<br/>
Kaynak işaretçisi.

*c*<br/>
Kopyalamanın son karakteri.

*biriktirme*<br/>
Karakter sayısı.

## <a name="return-value"></a>Dönüş Değeri

*C* karakteri kopyalanırsa, **_memccpy** , karakterden hemen sonraki bir karakter için bir işaretçi döndürür. *C* kopyalanmadığı takdirde **null**döndürür.

## <a name="remarks"></a>Açıklamalar

**_Memccpy** işlevi, *src* 'nin 0 veya daha fazla karakterini *hedefe*kopyalar, *c* karakteri kopyalandığında veya *sayı* karakterleri kopyalandığında, hangisi önce gelirse.

**Güvenlik notunun** Hedef arabelleğinin boyut veya Kaynak arabelleğinden daha büyük olduğundan emin olun. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_memccpy**|\<Memory. h > veya \<String. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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
