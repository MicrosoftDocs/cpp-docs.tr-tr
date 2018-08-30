---
title: memmove, wmemmove | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- memmove
- wmemmove
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
- ntdll.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- memmove
- wmemmove
dev_langs:
- C++
helpviewer_keywords:
- wmemmove function
- memmove function
ms.assetid: 3a906114-9cf3-40d7-bd99-ee452004f218
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11f474675d8ba5b370b1f13f048e989d9c283bde
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204634"
---
# <a name="memmove-wmemmove"></a>memmove, wmemmove

Bir arabellek diğerine taşır. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [memmove_s, wmemmove_s](memmove-s-wmemmove-s.md).

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

*Hedef*<br/>
Hedef nesne.

*src*<br/>
Kaynak nesne.

*Sayısı*<br/>
Bayt sayısı (**memmove**) veya karakterleri (**wmemmove**) kopyalamak için.

## <a name="return-value"></a>Dönüş Değeri

Değerini *dest*.

## <a name="remarks"></a>Açıklamalar

Kopya *sayısı* bayt (**memmove**) veya karakterleri (**wmemmove**) öğesinden *src* için *dest*. Bazı kaynak alanını ve hedef bölgelerini çakışırsa, her iki işlev çakışan bölgede özgün kaynak bayt üzerine önce kopyalandığından emin olun.

**Güvenlik Notu** boyutta veya daha büyük kaynak arabelleği hedef arabellek aynı olduğundan emin olun. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

**Memmove** ve **wmemmove** işlevleri yalnızca kullanımdan kaldırılacaktır varsa sabiti **_CRT_SECURE_DEPRECATE_MEMORY** ekleme deyimi için sırayla önce tanımlanır kullanım dışı, aşağıdaki örnekte olduğu gibi olmasını İşlevler:

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
|**memmove**|\<String.h >|
|**wmemmove**|\<wchar.h >|

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

[Ara Bellek Düzenlemesi](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
