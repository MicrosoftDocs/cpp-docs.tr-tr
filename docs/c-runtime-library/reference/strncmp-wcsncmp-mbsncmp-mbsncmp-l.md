---
title: strncmp, wcsncmp, _mbsncmp, _mbsncmp_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- strncmp
- _mbsncmp
- wcsncmp
- _mbsncmp_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ftcsnccmp
- _ftcsncmp
- _tcsncmp
- _tcsnccmp
- strncmp
- _mbsncmp
- wcsncmp
dev_langs:
- C++
helpviewer_keywords:
- _tcsnccmp function
- ftcsncmp function
- wcsncmp function
- _ftcsncmp function
- _mbsncmp function
- tcsncmp function
- mbsncmp function
- _mbsncmp_l function
- mbsncmp_l function
- strncmp function
- strings [C++], comparing characters of
- string comparison [C++], strncmp function
- _tcsncmp function
- tcsnccmp function
- ftcsnccmp function
- characters [C++], comparing
- _ftcsnccmp function
ms.assetid: 2fdbf4e6-77da-4b59-9086-488f6066b8af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a64d7248151287f4f2af38e666db62f9a15d833f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="strncmp-wcsncmp-mbsncmp-mbsncmpl"></a>strncmp, wcsncmp, _mbsncmp, _mbsncmp_l

Belirtilen iki dize karakterlerini sayısı kadar karşılaştırır.

> [!IMPORTANT]
> **_mbsncmp** ve **_mbsncmp_l** Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int strncmp(
   const char *string1,
   const char *string2,
   size_t count
);
int wcsncmp(
   const wchar_t *string1,
   const wchar_t *string2,
   size_t count
);
int _mbsncmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsncmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);int _mbsnbcmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
```

### <a name="parameters"></a>Parametreler

*Dize1*, *dize2*<br/>
Karşılaştırılacak dizeleri.

*Sayısı*<br/>
Karşılaştırılacak karakter sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Alt dizeler ilişkisi dönüş değerini gösteren *Dize1* ve *dize2* gibi.

|Dönüş değeri|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* substring değerinden *dize2* substring|
|0|*Dize1* substring aynı *dize2* substring|
|> 0|*Dize1* substring büyük *dize2* substring|

Parametre doğrulama hata **_mbsncmp** ve **_mbsncmp_l** dönmek **_NLSCMPERROR**, içinde tanımlanan \<string.h > ve \< Mbstring.h >.

## <a name="remarks"></a>Açıklamalar

**Strncmp** işlevi gerçekleştiren bir sıralı karşılaştırma en fazla ilk *sayısı* içinde karakterleri *Dize1* ve *dize2* ve alt dizeler arasındaki ilişkiyi gösteren bir değer döndürür. **strncmp** büyük küçük harfe duyarlı bir sürümü **_strnicmp**. **wcsncmp** ve **_mbsncmp** büyük küçük harfe duyarlı sürümleri **_wcsnicmp** ve **_mbsnicmp**.

**wcsncmp** ve **_mbsncmp** joker karakter ve çok baytlı karakter sürümleri **strncmp**. Bağımsız değişkenleri **wcsncmp** joker karakter olan dizeleri; bu **_mbsncmp** çok baytlı karakter dizeleri belirtilmiştir. **_mbsncmp** birden çok baytlı kod sayfasına göre çok baytlı karakter sıralarının tanır ve döndürür **_NLSCMPERROR** bir hata.

Ayrıca, **_mbsncmp** ve **_mbsncmp_l** parametreleri doğrulayın. Varsa *Dize1* veya *dize2* null işaretçi açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **_mbsncmp** ve **_mbsncmp_l** dönmek **_NLSCMPERROR** ve **errno** için  **EINVAL**. **strncmp** ve **wcsncmp** parametrelerini doğrulamaz. Bu işlevler aynı şekilde aksi davranır.

Karşılaştırma davranışını **_mbsncmp** ve **_mbsncmp_l** ayarı tarafından etkilenen **LC_CTYPE** yerel kategori ayarı. Bu, birden çok baytlı karakterler baştaki ve sondaki bayt algılanması denetler. Daha fazla bilgi için bkz: [setlocale](setlocale-wsetlocale.md). **_Mbsncmp** işlevi için bu yerel ayara bağımlı davranış geçerli yerel ayarı kullanır. **_Mbsncmp_l** kullanır ancak bu işlevi aynı *yerel* parametre yerine. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md). Yerel bir tek baytlı yerel ise, bu işlevler davranışını aynıdır **strncmp**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnccmp**|**strncmp**|**_mbsncmp**|**wcsncmp**|
|**_tcsncmp**|**strncmp**|**_mbsnbcmp**|**wcsncmp**|
|**_tccmp**|Makro veya satır içi işlev eşlemeleri|**_mbsncmp**|Makro veya satır içi işlev eşlemeleri|
|**Geçerli değil**|**Geçerli değil**|**_mbsncmp_l**|**Geçerli değil**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strncmp**|\<String.h >|
|**wcsncmp**|\<String.h > veya \<wchar.h >|
|**_mbsncmp**, **_mbsncmp_l**|\<Mbstring.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_strncmp.c
#include <string.h>
#include <stdio.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown fox jumps over the lazy dog";

int main( void )
{
   char tmp[20];
   int result;
   printf( "Compare strings:\n      %s\n      %s\n\n",
           string1, string2 );
   printf( "Function:   strncmp (first 10 characters only)\n" );
   result = strncmp( string1, string2 , 10 );
   if( result > 0 )
      strcpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, sizeof(tmp), "less than" );
   else
      strcpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:      String 1 is %s string 2\n\n", tmp );
   printf( "Function:   strnicmp _strnicmp (first 10 characters only)\n" );
   result = _strnicmp( string1, string2, 10 );
   if( result > 0 )
      strcpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, sizeof(tmp), "less than" );
   else
      strcpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:      String 1 is %s string 2\n", tmp );
}
```

```Output
Compare strings:
      The quick brown dog jumps over the lazy fox
      The QUICK brown fox jumps over the lazy dog

Function:   strncmp (first 10 characters only)
Result:      String 1 is greater than string 2

Function:   strnicmp _strnicmp (first 10 characters only)
Result:      String 1 is equal to string 2
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
