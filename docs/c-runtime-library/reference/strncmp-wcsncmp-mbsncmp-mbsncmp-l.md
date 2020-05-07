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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: deae95f8cf7d538dfe22ebbe0e86524765d9d234
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919322"
---
# <a name="strncmp-wcsncmp-_mbsncmp-_mbsncmp_l"></a>strncmp, wcsncmp, _mbsncmp, _mbsncmp_l

İki dizenin belirtilen sayıda karakter ile karşılaştırılır.

> [!IMPORTANT]
> **_mbsncmp** ve **_mbsncmp_l** , Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Karşılaştırılacak dizeler.

*biriktirme*<br/>
Karşılaştırılacak karakter sayısı.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri, *Dize1* ve *dize2* alt dizelerinin aşağıdaki gibi ilişkisini gösterir.

|Döndürülen değer|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* substring, *dize2* alt dizenden küçük|
|0|*Dize1* alt dizesi, *dize2* alt dizesi ile özdeş|
|> 0|*Dize1* alt dize, *dize2* alt dizeden büyük|

Bir parametre doğrulama hatası üzerinde **_mbsncmp** ve **_mbsncmp_l** String. h> ve \<mbstring. \<h> içinde tanımlanan **_NLSCMPERROR**döndürün.

## <a name="remarks"></a>Açıklamalar

**Strncmp** işlevi, *Dize1* ve *dize2* içindeki ilk *sayı* karakterlerinin en fazla bir sıralı karşılaştırmasını gerçekleştirir ve alt dizeler arasındaki ilişkiyi gösteren bir değer döndürür. **strncmp** , büyük/küçük harfe duyarlı bir **_strnicmp**sürümüdür. **wcsncmp** ve **_mbsncmp** , **_wcsnicmp** ve **_mbsnicmp**'ın büyük/küçük harfe duyarlı sürümleridir.

**wcsncmp** ve **_mbsncmp** , **strncmp**'nin geniş karakterli ve çok baytlı karakter sürümleridir. **Wcsncmp** bağımsız değişkenleri geniş karakterli dizelerdir; **_mbsncmp** olanlar çok baytlı karakter dizeleridir. **_mbsncmp** çok baytlı karakter dizilerini bir çok baytlı kod sayfasına göre tanır ve bir hata üzerinde **_NLSCMPERROR** döndürür.

Ayrıca, **_mbsncmp** ve **_mbsncmp_l** parametreleri doğrula. *Dize1* veya *dize2* null Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **_mbsncmp** ve **_mbsncmp_l** **_NLSCMPERROR** döndürün ve **errno** öğesini **EINVAL**olarak ayarlayın. **strncmp** ve **wcsncmp** parametrelerini doğrulamaz. Bu işlevler, aynı şekilde davranır.

**_Mbsncmp** ve **_mbsncmp_l** karşılaştırma davranışı, yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir. Bu denetim, çok baytlı karakterlerin baştaki ve sondaki baytlarını tespit eder. Daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md). **_Mbsncmp** işlevi, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_Mbsncmp_l** işlevi, bunun yerine *yerel ayar* parametresini kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md). Yerel ayar tek baytlık bir yerel ayar ise, bu işlevlerin davranışı **strncmp**ile aynıdır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnccmp**|**strncmp**|**_mbsncmp**|**wcsncmp**|
|**_tcsncmp**|**strncmp**|**_mbsnbcmp**|**wcsncmp**|
|**_tccmp**|Makroya veya satır içi işleve eşlenir|**_mbsncmp**|Makroya veya satır içi işleve eşlenir|
|**uygulanamaz**|**uygulanamaz**|**_mbsncmp_l**|**uygulanamaz**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strncmp**|\<String. h>|
|**wcsncmp**|\<String. h> veya \<wchar. h>|
|**_mbsncmp**, **_mbsncmp_l**|\<mbstring. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
