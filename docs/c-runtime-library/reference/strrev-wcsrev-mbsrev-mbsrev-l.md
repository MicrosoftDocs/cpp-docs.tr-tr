---
title: _strrev, _wcsrev, _mbsrev, _mbsrev_l
ms.date: 4/2/2020
api_name:
- _wcsrev
- _mbsrev
- _strrev
- _mbsrev_l
- _o__mbsrev
- _o__mbsrev_l
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _strrev
- _ftcsrev
- _tcsrev
- mbsrev
- mbsrev_l
- _wcsrev_fstrrev
- _mbsrev
helpviewer_keywords:
- _mbsrev_l function
- characters [C++], switching
- _mbsrev function
- strrev function
- _ftcsrev function
- strings [C++], reversing
- wcsrev function
- _strrev function
- mbsrev_l function
- reversing characters in strings
- ftcsrev function
- characters [C++], reversing order
- _wcsrev function
- mbsrev function
- tcsrev function
- _tcsrev function
ms.assetid: 87863e89-4fa0-421c-af48-25d8516fe72f
ms.openlocfilehash: 585cdae15572eca565d2779225737a014d5f7837
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365037"
---
# <a name="_strrev-_wcsrev-_mbsrev-_mbsrev_l"></a>_strrev, _wcsrev, _mbsrev, _mbsrev_l

Bir dizenin karakterlerini tersine çevirir.

> [!IMPORTANT]
> **_mbsrev** ve **_mbsrev_l,** Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
char *_strrev(
   char *str
);
wchar_t *_wcsrev(
   wchar_t *str
);
unsigned char *_mbsrev(
   unsigned char *str
);
unsigned char *_mbsrev_l(
   unsigned char *str,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Ters çevirmek için null-sonlandırılan dize.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Değiştirilen dize için bir işaretçi döndürür. Bir hatayı belirtmek için hiçbir iade değeri ayrılmıştır.

## <a name="remarks"></a>Açıklamalar

**_strrev** işlevi *str'deki*karakterlerin sırasını tersine çevirir. Sonlandırıcı null karakter yerinde kalır. **_wcsrev** ve **_mbsrev** **_strrev**geniş karakterli ve çok bayt karakterli versiyonlarıdır. **_wcsrev** bağımsız değişkenleri ve getiri değeri geniş karakterli dizeleridir; **_mbsrev** çok bayt karakterli dizeleri vardır. _mbsrev **_mbsrev**için, *str* her çok bayt karakter bayt sırası değişmez. Bu üç işlev aynı şekilde çalışır.

**_mbsrev** parametrelerini doğrular. *String1* veya *string2* null işaretçisi ise, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, **_mbsrev** **NULL** döndürür ve **EINVAL** **için errno** ayarlar. **_strrev** ve **_wcsrev** parametrelerini doğrulamaz.

Çıktı değeri, yerel LC_CTYPE **kategori** ayarı ayarı etkilenir; daha fazla bilgi için [setlocale, _wsetlocale](setlocale-wsetlocale.md) bakın. Bu işlevlerin sürümleri aynıdır, **ancak _l** soneki olmayanlar geçerli yerel alanı kullanır ve **_l** soneki olanlar bunun yerine geçirilen yerel parametreyi kullanır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

> [!IMPORTANT]
> Bu işlevler arabellek taşma tehditlerine karşı savunmasız olabilir. Arabellek taşmaları, gereksiz bir ayrıcalık yükselmesine neden olabileceğinden sistem saldırıları için kullanılabilir. Daha fazla bilgi için [bkz.](/windows/win32/SecBP/avoiding-buffer-overruns)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsrev**|**_strrev**|**_mbsrev**|**_wcsrev**|
|**Yok**|**Yok**|**_mbsrev_l**|**Yok**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strrev**|\<string.h>|
|**_wcsrev**|\<string.h> \<veya wchar.h>|
|**_mbsrev**, **_mbsrev_l**|\<mbstring.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_strrev.c
// This program checks a string to see
// whether it is a palindrome: that is, whether
// it reads the same forward and backward.
//

#include <string.h>
#include <stdio.h>

int main( void )
{
   char* string = "Able was I ere I saw Elba";
   int result;

   // Reverse string and compare (ignore case):
   result = _stricmp( string, _strrev( _strdup( string ) ) );
   if( result == 0 )
      printf( "The string \"%s\" is a palindrome\n", string );
   else
      printf( "The string \"%s\" is not a palindrome\n", string );
}
```

```Output
The string "Able was I ere I saw Elba" is a palindrome
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
