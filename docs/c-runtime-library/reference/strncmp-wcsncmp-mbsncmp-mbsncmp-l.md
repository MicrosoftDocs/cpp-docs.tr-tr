---
title: strncmp, wcsncmp, _mbsncmp, _mbsncmp_l
ms.date: 4/2/2020
api_name:
- strncmp
- _mbsncmp
- wcsncmp
- _mbsncmp_l
- _o__mbsncmp
- _o__mbsncmp_l
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
- _ftcsnccmp
- _ftcsncmp
- _tcsncmp
- _tcsnccmp
- strncmp
- _mbsncmp
- wcsncmp
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
ms.openlocfilehash: fa253bbf7b0ea2ae9993edb12843245b2a1065ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364195"
---
# <a name="strncmp-wcsncmp-_mbsncmp-_mbsncmp_l"></a>strncmp, wcsncmp, _mbsncmp, _mbsncmp_l

İki dizekarakter belirtilen sayısı kadar karşılaştırır.

> [!IMPORTANT]
> **_mbsncmp** ve **_mbsncmp_l,** Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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

*string1*, *string2*<br/>
Karşılaştırılacak dizeleri.

*Sayısı*<br/>
Karşılaştırılacak karakter sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

İade değeri *string1* ve *string2* alt dizeleri arasındaki ilişkiyi aşağıdaki gibi gösterir.

|Döndürülen değer|Açıklama|
|------------------|-----------------|
|< 0|*string1 string2* *string2* substring daha az substring|
|0|*string1* substring *string2* substring aynı|
|> 0|*string1* alt dize *string2* substring daha büyük|

Bir parametre doğrulama hatasında, \<string.h> ve mbstring.h \<> tanımlanan **_NLSCMPERROR _mbsncmp** ve **_mbsncmp_l** döndürün. **_NLSCMPERROR**

## <a name="remarks"></a>Açıklamalar

**strncmp** işlevi *string1* ve *string2'deki* en çok ilk *sayım* karakterlerinin bir ordinal karşılaştırmasını gerçekleştirir ve alt dizeleri arasındaki ilişkiyi gösteren bir değer döndürür. **strncmp** **_strnicmp**bir büyük/küçük harf duyarlı sürümüdür. **wcsncmp** ve **_mbsncmp** **_wcsnicmp** ve **_mbsnicmp**vaka duyarlı sürümleridir.

**wcsncmp** ve **_mbsncmp** **strncmp**geniş karakterli ve multibayt karakterli sürümleridir. **wcsncmp** bağımsız değişkenleri geniş karakterdizeleri vardır; **_mbsncmp** çok bayt karakterli dizeleri vardır. **_mbsncmp** çok baytlı kod sayfasına göre çok bayt karakter dizilerini tanır ve bir hata üzerine **_NLSCMPERROR** döndürür.

Ayrıca, **_mbsncmp** ve **_mbsncmp_l** parametreleri doğrular. *String1* veya *string2* null işaretçisi ise, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, **_mbsncmp** ve **_mbsncmp_l** **_NLSCMPERROR** dönmek ve **EINVAL** **için errno** ayarlayın. **strncmp** ve **wcsncmp** parametrelerini doğrulamaz. Bu işlevler aynı şekilde başka türlü çalışır.

**_mbsncmp** ve **_mbsncmp_l** karşılaştırma davranışı, yerel LC_CTYPE **kategori** ayarı ayarı etkilenir. Bu, çok bayt karakter in ilerler ve baytlarını algılatır. Daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md)bakın. **_mbsncmp** işlevi, bu yerele bağımlı davranış için geçerli yerel alanı kullanır. **_mbsncmp_l** işlevi, bunun yerine *yerel* parametreyi kullanması dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın. Yerel bir tek bayt yerel ise, bu işlevlerin davranışı **strncmp**ile aynıdır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnccmp**|**strncmp**|**_mbsncmp**|**wcsncmp**|
|**_tcsncmp**|**strncmp**|**_mbsnbcmp**|**wcsncmp**|
|**_tccmp**|Makro veya satır çizgisi işlevine eşler|**_mbsncmp**|Makro veya satır çizgisi işlevine eşler|
|**geçerli değildir**|**geçerli değildir**|**_mbsncmp_l**|**geçerli değildir**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strncmp**|\<string.h>|
|**wcsncmp**|\<string.h> \<veya wchar.h>|
|**_mbsncmp**, **_mbsncmp_l**|\<mbstring.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
