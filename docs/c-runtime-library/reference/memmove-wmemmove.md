---
description: 'Hakkında daha fazla bilgi edinin: memmove, wmemmove'
title: memmove, wmemmove
ms.date: 11/04/2016
api_name:
- memmove
- wmemmove
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
- ntdll.dll
- ucrtbase.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- memmove
- wmemmove
helpviewer_keywords:
- wmemmove function
- memmove function
ms.assetid: 3a906114-9cf3-40d7-bd99-ee452004f218
ms.openlocfilehash: 15dee8eab2a1b7eedd3891d8673647a711c0e499
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97171393"
---
# <a name="memmove-wmemmove"></a>memmove, wmemmove

Bir arabelleği diğerine gider. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [memmove_s, wmemmove_s](memmove-s-wmemmove-s.md).

## <a name="syntax"></a>Sözdizimi

```C
void *memmove(
   void *dest,
   const void *src,
   size_t count
);
wchar_t *wmemmove(
   wchar_t *dest,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>Parametreler

*HD*<br/>
Hedef nesne.

*src*<br/>
Kaynak nesne.

*biriktirme*<br/>
Kopyalanacak bayt (**memmove**) veya karakter (**wmemmove**) sayısı.

## <a name="return-value"></a>Dönüş Değeri

*Hedef* değeri.

## <a name="remarks"></a>Açıklamalar

*Src* 'den *hedefe* kadar olan *sayı* baytlarını (**memmove**) veya karakterleri (**wmemmove**) kopyalar. Kaynak alanın ve hedefin bazı bölgeleri çakışırsa, her iki işlev de çakışan bölgedeki özgün kaynak baytlarının üzerine yazılmadan önce kopyalanmasını güvence altına alınır.

**Güvenlik notunun** Hedef arabelleğinin boyut veya Kaynak arabelleğinden daha büyük olduğundan emin olun. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

**Memmove** ve **wmemmove** işlevleri, işlevlerin kullanım dışı olması için aşağıdaki örnekte olduğu gibi, yalnızca sabit **_CRT_SECURE_DEPRECATE_MEMORY** dahil etme ifadesiyle önce tanımlanmışsa kullanım dışı bırakılır:

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <string.h>
```

veya

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <wchar.h>
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**memmove**|\<string.h>|
|**wmemmove**|\<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_memcpy.c
// Illustrate overlapping copy: memmove
// always handles it correctly; memcpy may handle
// it correctly.
//

#include <memory.h>
#include <string.h>
#include <stdio.h>

char str1[7] = "aabbcc";

int main( void )
{
   printf( "The string: %s\n", str1 );
   memcpy( str1 + 2, str1, 4 );
   printf( "New string: %s\n", str1 );

   strcpy_s( str1, sizeof(str1), "aabbcc" );   // reset string

   printf( "The string: %s\n", str1 );
   memmove( str1 + 2, str1, 4 );
   printf( "New string: %s\n", str1 );
}
```

```Output
The string: aabbcc
New string: aaaabb
The string: aabbcc
New string: aaaabb
```

## <a name="see-also"></a>Ayrıca bkz.

[Arabellek Işleme](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
