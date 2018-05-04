---
title: _memicmp, _memicmp_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _memicmp_l
- _memicmp
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
- _memicmp
- memicmp_l
- _memicmp_l
dev_langs:
- C++
helpviewer_keywords:
- memicmp function
- _memicmp function
- memicmp_l function
- _memicmp_l function
ms.assetid: 0a6eb945-4077-4f84-935d-1aaebe8db8cb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3ddd09fbfbfd4de095bfbc67bc669cf9c794dee
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="memicmp-memicmpl"></a>_memicmp, _memicmp_l

İki arabellekler (büyük küçük harf duyarsız) karakter karşılaştırır.

## <a name="syntax"></a>Sözdizimi

```C
int _memicmp(
   const void *buffer1,
   const void *buffer2,
   size_t count
);
int _memicmp_l(
   const void *buffer1,
   const void *buffer2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*buffer1*<br/>
İlk arabelleği.

*buffer2*<br/>
İkinci bir arabellek.

*Sayısı*<br/>
Karakter sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri arabellek arasındaki ilişkiyi gösterir.

|Dönüş değeri|İlk sayı bayt buf1 ve buf2 ilişkisi|
|------------------|--------------------------------------------------------|
|< 0|*buffer1* değerinden *buffer2*.|
|0|*buffer1* aynı *buffer2*.|
|> 0|*buffer1* büyük *buffer2*.|
|**_NLSCMPERROR**|Bir hata oluşmuştur.|

## <a name="remarks"></a>Açıklamalar

**_Memicmp** işlevi karşılaştırır ilk *sayısı* iki arabellekleri karakterlerden *buffer1* ve *buffer2* bayt. Karşılaştırma büyük küçük harfe duyarlı değildir.

Her iki *buffer1* veya *buffer2* null işaretçi açıklandığı gibi bir geçersiz parametre işleyicisi bu işlevi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, işlevi döndürür **_NLSCMPERROR** ve ayarlar **errno** için **EINVAL**.

**_memicmp** geçerli yerel ayar için yerel ayara bağımlı davranışı; kullanır **_memicmp_l** yerine geçirilen yerel ayar kullandığı dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_memicmp**|\<Memory.h > veya \<string.h >|
|**_memicmp_l**|\<Memory.h > veya \<string.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_memicmp.c
// This program uses _memicmp to compare
// the first 29 letters of the strings named first and
// second without regard to the case of the letters.

#include <memory.h>
#include <stdio.h>
#include <string.h>

int main( void )
{
   int result;
   char first[] = "Those Who Will Not Learn from History";
   char second[] = "THOSE WHO WILL NOT LEARN FROM their mistakes";
   // Note that the 29th character is right here ^

   printf( "Compare '%.29s' to '%.29s'\n", first, second );
   result = _memicmp( first, second, 29 );
   if( result < 0 )
      printf( "First is less than second.\n" );
   else if( result == 0 )
      printf( "First is equal to second.\n" );
   else if( result > 0 )
      printf( "First is greater than second.\n" );
}
```

```Output
Compare 'Those Who Will Not Learn from' to 'THOSE WHO WILL NOT LEARN FROM'
First is equal to second.
```

## <a name="see-also"></a>Ayrıca bkz.

[Ara Bellek Düzenlemesi](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
