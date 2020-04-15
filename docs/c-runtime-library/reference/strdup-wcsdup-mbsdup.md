---
title: _strdup, _wcsdup, _mbsdup
ms.date: 4/2/2020
api_name:
- _strdup
- _mbsdup
- _wcsdup
- _o__strdup
- _o__wcsdup
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcsdup
- mbsdup
- _mbsdup
- _strdup
- _ftcsdup
- _wcsdup
helpviewer_keywords:
- wcsdup function
- ftcsdup function
- _ftcsdup function
- mbsdup function
- strdup function
- _strdup function
- _wcsdup function
- copying strings
- duplicating strings
- strings [C++], copying
- _mbsdup function
- strings [C++], duplicating
- tcsdup function
- _tcsdup function
ms.assetid: 8604f8bb-95e9-45d3-93ef-20397ebf247a
ms.openlocfilehash: 7ad28633844c49ce5b86c8f71f4502c62eba1216
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359701"
---
# <a name="_strdup-_wcsdup-_mbsdup"></a>_strdup, _wcsdup, _mbsdup

Dizeleri çoğaltıyor.

> [!IMPORTANT]
> **_mbsdup** Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
char *_strdup(
   const char *strSource
);
wchar_t *_wcsdup(
   const wchar_t *strSource
);
unsigned char *_mbsdup(
   const unsigned char *strSource
);
```

### <a name="parameters"></a>Parametreler

*strSource*<br/>
Null-sonlandırılan kaynak dize.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, depolama alanı tahsis edilemiyorsa, kopyalanan dize veya **NULL** için depolama konumuna bir işaretçi döndürür.

## <a name="remarks"></a>Açıklamalar

**_strdup** *işlevi, strSource'un* bir kopyası için depolama alanı ayırmak için [malloc'u](malloc.md) çağırır ve daha sonra *strSource'u* ayrılan alana kopyalar.

**_wcsdup** ve **_mbsdup** **_strdup**geniş karakterli ve çok bayt karakterli versiyonlarıdır. _wcsdup bağımsız **değişkenleri** ve geri dönüş değeri geniş karakterli dizeleridir; **_mbsdup** çok bayt karakterli dizeleri vardır. Bu üç işlev aynı şekilde çalışır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsdup**|**_strdup**|**_mbsdup**|**_wcsdup**|

**strSource** kopyası için depolama alanı ayırmak için *strSource* **malloc** çağırır _strdup çünkü, **_strdup**için çağrı tarafından döndürülen işaretçi [üzerinde ücretsiz](free.md) rutin çağırarak bu belleği serbest bırakmak için her zaman iyi bir uygulamadır.

**_DEBUG** ve **_CRTDBG_MAP_ALLOC** tanımlanırsa, **_strdup** ve **_wcsdup,** hata ayıklama bellek ayırmalarına izin vermek için **_strdup_dbg** ve **_wcsdup_dbg** çağrılarıyla değiştirilir. Daha fazla bilgi için [_strdup_dbg _wcsdup_dbg.](strdup-dbg-wcsdup-dbg.md)

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strdup**|\<string.h>|
|**_wcsdup**|\<string.h> \<veya wchar.h>|
|**_mbsdup**|\<mbstring.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_strdup.c

#include <string.h>
#include <stdio.h>

int main( void )
{
   char buffer[] = "This is the buffer text";
   char *newstring;
   printf( "Original: %s\n", buffer );
   newstring = _strdup( buffer );
   printf( "Copy:     %s\n", newstring );
   free( newstring );
}
```

```Output
Original: This is the buffer text
Copy:     This is the buffer text
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
