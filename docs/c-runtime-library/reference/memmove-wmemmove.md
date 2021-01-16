---
description: 'Hakkında daha fazla bilgi edinin: memmove, wmemmove'
title: memmove, wmemmove
ms.date: 1/14/2021
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 6f9942c232710585aa5837510f0f04e5db36fb2a
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243131"
---
# <a name="memmove-wmemmove"></a>`memmove`, `wmemmove`

Bir arabelleği diğerine gider. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [ `memmove_s` , `wmemmove_s` ](memmove-s-wmemmove-s.md).

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

*`dest`*\
Hedef nesne.

*`src`*\
Kaynak nesne.

*`count`*\
Kopyalanacak bayt ( **`memmove`** ) veya karakter ( **`wmemmove`** ) sayısı.

## <a name="return-value"></a>Dönüş Değeri

Değeri *`dest`* .

## <a name="remarks"></a>Açıklamalar

*`count`* Bayt ( **`memmove`** ) veya karakter ( **`wmemmove`** ) öğesini öğesinden kopyalar *`src`* *`dest`* . Kaynak alanın ve hedefin bazı bölgeleri çakışırsa, her iki işlev de çakışan bölgedeki özgün kaynak baytlarının üzerine yazılmadan önce kopyalanmasını güvence altına alınır.

**Güvenlik notunun** Hedef arabelleğinin boyut veya Kaynak arabelleğinden daha büyük olduğundan emin olun. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

**`memmove`** Ve **`wmemmove`** işlevleri, **`_CRT_SECURE_DEPRECATE_MEMORY`** Aşağıdaki örnekte olduğu gibi işlevlerin kullanım dışı olması için ekleme ifadesinden önce belirtilmişse kullanım dışı bırakılır:

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
|**`memmove`**|`<string.h>`|
|**`wmemmove`**|`<wchar.h>`|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Arabellek Işleme](../../c-runtime-library/buffer-manipulation.md)\
[`_memccpy`](memccpy.md)\
[`memcpy`, `wmemcpy`](memcpy-wmemcpy.md)\
[`strcpy`, `wcscpy`, `_mbscpy`](strcpy-wcscpy-mbscpy.md)\
[`strncpy`, `_strncpy_l`, `wcsncpy`, `_wcsncpy_l`, `_mbsncpy`, `_mbsncpy_l`](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)\
