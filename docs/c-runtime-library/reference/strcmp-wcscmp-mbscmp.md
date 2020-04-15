---
title: strcmp, wcscmp, _mbscmp, _mbscmp_l
ms.date: 4/2/2020
api_name:
- wcscmp
- _mbscmp
- _mbscmp_l
- strcmp
- _o__mbscmp
- _o__mbscmp_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbscmp
- _mbscmp_l
- wcscmp
- strcmp
- _tcscmp
- _ftcscmp
helpviewer_keywords:
- tcscmp function
- strcmp function
- strings [C++], comparing
- mbscmp function
- string comparison [C++]
- _mbscmp function
- _mbscmp_l function
- wcscmp function
- _tcscmp function
- _ftcscmp function
- ftcscmp function
ms.assetid: 5d216b57-7a5c-4cb3-abf0-0f4facf4396d
ms.openlocfilehash: 16bb294f7bbdc0b95b59b845d7b714f823f9d962
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81357280"
---
# <a name="strcmp-wcscmp-_mbscmp-_mbscmp_l"></a>strcmp, wcscmp, _mbscmp, _mbscmp_l

Dizeleri karşılaştırın.

> [!IMPORTANT]
> **_mbscmp** ve **_mbscmp_l,** Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int strcmp(
   const char *string1,
   const char *string2
);
int wcscmp(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbscmp(
   const unsigned char *string1,
   const unsigned char *string2
);
int _mbscmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*string1*, *string2*<br/>
Karşılaştırmak için null-sonlandırılan dizeleri.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri için geri dönüş değeri *string1* ile string2 arasındaki ordinal ilişkisini *gösterir.*

|Değer|String1 ile string2 arasındaki ilişki|
|-----------|----------------------------------------|
|< 0|*string1* *string2'den* daha azdır|
|0|*string1* *string2* ile aynıdır|
|> 0|*string1* *string2'den* büyüktür|

Bir parametre doğrulama hatasında, \<string.h> ve mbstring.h \<> tanımlanan _NLSCMPERROR **_mbscmp** ve **_mbscmp_l** döndürün. **_NLSCMPERROR**

## <a name="remarks"></a>Açıklamalar

**strcmp** işlevi *string1* ve *string2'nin* bir ordinal karşılaştırmasını gerçekleştirir ve ilişkilerini gösteren bir değer döndürür. **wcscmp** ve **_mbscmp,** sırasıyla, **strcmp**geniş karakterli ve multibayt karaktersürümleri. **_mbscmp** geçerli çok bayt kod sayfasına göre çok bayt karakter dizilerini tanır ve bir hata üzerine **_NLSCMPERROR** döndürür. **_mbscmp_l** aynı davranışa sahiptir, ancak geçerli yerel alan yerine geçen yerel parametreyi kullanır. Daha fazla bilgi için [Kod Sayfaları'na](../../c-runtime-library/code-pages.md)bakın. Ayrıca, *string1* veya *string2* null işaretçisi ise, **_mbscmp** [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütme devam etmesine izin verilirse, **_mbscmp** ve **_mbscmp_l** **_NLSCMPERROR** dönmek ve **EINVAL** **için errno** ayarlayın. **strcmp** ve **wcscmp** parametrelerini doğrulamaz. Bu işlevler aynı şekilde başka türlü çalışır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscmp**|**strcmp**|**_mbscmp**|**wcscmp**|

**Strcmp** işlevleri **strcmp** karşılaştırmaları ordinal olduğu **strcoll** işlevleri farklıdır, ve yerel etkilenmez. **strcoll,** geçerli yerel LC_COLLATE **kategorisini** kullanarak dizeleri lexicographically karşılaştırır. **LC_COLLATE** kategorisi hakkında daha fazla bilgi için [setlocale, _wsetlocale'](setlocale-wsetlocale.md)a bakın.

"C" yerel sinde, karakter kümesindeki (ASCII karakter kümesi) karakter sırası lexicographic karakter sırası ile aynıdır. Ancak, diğer yerel ayarlarda, karakter kümesindeki karakterlerin sırası lexicographic sırasına göre farklılık gösterebilir. Örneğin, bazı Avrupa yerel bölgelerinde , 'a' (değer 0x61) karakteri kümesindeki 'ä' (değer 0xE4) karakterinden önce gelir, ancak 'ä' karakteri 'a' lexicographically karakterinin önüne gelir.

Karakter kümesi ile lexicographic karakter sırasının farklı olduğu yerel ayarlarda, dizelerin lexicographic karşılaştırması için **strcmp** yerine **strcoll'u** kullanabilirsiniz. Alternatif olarak, özgün dizelerüzerinde **strxfrm** ve sonra elde edilen dizeleri **strcmp** kullanabilirsiniz.

**Strcmp** fonksiyonları büyük/küçük harf duyarlıdır. stricmp , ** \_wcsicmp**, ve ** \_mbsicmp** ilk küçük formları dönüştürerek dizeleri karşılaştırın. ** \_** ASCII tablosunda 'Z' ve 'a' arasında yer alan karakterler içeren iki dize\\('',, ',','],',^', '_'ve ' ')\`durumlarına bağlı olarak farklı karşılaştırılır. Örneğin, karşılaştırma küçük ("abcde" > "abcd^") ve diğer yol ("ABCDE" < "ABCD^") ise, karşılaştırma büyük harfle karşılanırsa, "ABCDE" ve "ABCD^" iki dizesini bir şekilde karşılaştırın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strcmp**|\<string.h>|
|**wcscmp**|\<string.h> \<veya wchar.h>|
|**_mbscmp**|\<mbstring.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

```C
// crt_strcmp.c

#include <string.h>
#include <stdio.h>
#include <stdlib.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown dog jumps over the lazy fox";

int main( void )
{
   char tmp[20];
   int result;

   // Case sensitive
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );
   result = strcmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );

   // Case insensitive (could use equivalent _stricmp)
   result = _stricmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof (tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );
}
```

```Output
Compare strings:
   The quick brown dog jumps over the lazy fox
   The QUICK brown dog jumps over the lazy fox

   strcmp:   String 1 is greater than string 2
   _stricmp:  String 1 is equal to string 2
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[_memicmp, _memicmp_l](memicmp-memicmp-l.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
