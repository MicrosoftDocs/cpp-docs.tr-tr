---
title: _stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l
ms.date: 11/04/2016
api_name:
- _stricmp_l
- _mbsicmp
- _wcsicmp
- _mbsicmp_l
- _stricmp
- _wcsicmp_l
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ftcsicmp
- _stricmp
- wcsicmp_l
- _wcsicmp
- _tcsicmp
- _strcmpi
- stricmp_l
- _mbsicmp
- _fstricmp
- mbsicmp_l
- mbsicmp
helpviewer_keywords:
- _wcsicmp function
- _stricmp_l function
- fstricmp function
- _tcsicmp function
- ftcsicmp function
- string comparison [C++], lowercase
- _wcsicmp_l function
- _fstricmp function
- strings [C++], comparing
- mbsicmp function
- _ftcsicmp function
- _mbsicmp_l function
- wcsicmp_l function
- _stricmp function
- _mbsicmp function
- tcsicmp function
- stricmp_l function
- mbsicmp_l function
- _strcmpi function
ms.assetid: 0e1ee515-0d75-435a-a445-8875d4669b50
ms.openlocfilehash: 108a3c572174be5048d0bba48a4da0f4a735f458
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940689"
---
# <a name="_stricmp-_wcsicmp-_mbsicmp-_stricmp_l-_wcsicmp_l-_mbsicmp_l"></a>_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l

Dizelerin büyük/küçük harf duyarsız bir karşılaştırmasını yapar.

> [!IMPORTANT]
> **_mbsıcmp** ve **_mbsicmp_l** Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _stricmp(
   const char *string1,
   const char *string2
);
int _wcsicmp(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbsicmp(
   const unsigned char *string1,
   const unsigned char *string2
);
int _stricmp_l(
   const char *string1,
   const char *string2,
   _locale_t locale
);
int _wcsicmp_l(
   const wchar_t *string1,
   const wchar_t *string2,
   _locale_t locale
);
int _mbsicmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Dize1*, *dize2*<br/>
Karşılaştırılacak null ile sonlandırılmış dizeler.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri, *Dize1* ile *dize2* arasındaki ilişkiyi aşağıda gösterildiği gibi gösterir.

|Dönüş değeri|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* küçüktür *dize2*|
|0|*Dize1* ile *dize2* özdeş|
|> 0|*dize2* 'den büyük *Dize1*|

Bir hatada, **_mbsıcmp** , \<String. h > ve \<mbstring. h > tanımlı **_NLSCMPERROR**döndürür.

## <a name="remarks"></a>Açıklamalar

**_Stricmp** işlevi, her karakteri küçük harfe dönüştürdükten sonra *Dize1* ve *dize2* 'yi karşılaştırır ve ilişkilerini gösteren bir değer döndürür. **_stricmp,** **_stricd karşılaştırmasının** yalnızca **LC_CTYPE**tarafından etkilendiğine göre, hangi karakterlerin büyük ve küçük harf olduğunu belirleyen **_stricoll** 'den farklıdır. **_Stricoll** işlevi, hem durumu hem de harmanlama sırasını içeren yerel ayarın **LC_CTYPE** ve **LC_COLLATE** kategorilerine göre dizeleri karşılaştırır. **LC_COLLATE** kategorisi hakkında daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md) ve [locale kategorileri](../../c-runtime-library/locale-categories.md). **_L** sonekine sahip olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. Sonekine sahip sürümler, bunun yerine geçirilen yerel ayarı kullanmaları dışında aynıdır. Yerel ayar ayarlanmamışsa, C yerel ayarı kullanılır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

> [!NOTE]
> **_stricmp** , **_strcmpi**ile eşdeğerdir. Bunlar birbirinin yerine kullanılabilir, ancak **_stricmp** tercih edilen standarttır.

**_Strcmpi** işlevi **_stricmp** ile eşdeğerdir ve yalnızca geriye dönük uyumluluk için sağlanır.

**_Stricmp** küçük harf karşılaştırmaları yaptığından, beklenmeyen davranışlara neden olabilir.

**_Stricmp** tarafından büyük/küçük harf dönüştürmenin bir karşılaştırmanın sonucunu etkilediği zaman göstermek için, iki DIZININ Johnston ve JOHN_HENRY olduğunu varsayalım. "_" Küçük harfli bir ASCII değerine sahip olduğu için JOHN_HENRY dizesi JOHNSTON 'tan daha az kabul edilir. Aslında, 91 ve 96 arasında bir ASCII değeri olan herhangi bir karakter herhangi bir harften daha az kabul edilir.

[Strcmp](strcmp-wcscmp-mbscmp.md) işlevi **_stricmp**yerine KULLANıLıRSA, JOHN_HENRY, Johnston 'den büyük olur.

**_wcsıcmp** ve **_mbsıcmp** , **_stricmp**'nin geniş karakterli ve çok baytlı karakter sürümleridir. **_Wcsıcmp** 'nin bağımsız değişkenleri ve dönüş değeri geniş karakterli dizelerdir; **_mbsıcmp** 'nin bu tür çok baytlı karakter dizeleridir. **_mbsıcmp** , geçerli çok baytlı kod sayfasına göre çok baytlı karakter dizilerini tanır ve hata üzerinde **_Nlscmperror** döndürür. Daha fazla bilgi için bkz. [kod sayfaları](../../c-runtime-library/code-pages.md). Bu üç işlev, aynı şekilde davranır.

**_wcsıcmp** ve **wcscmp** , bunları karşılaştırmadan önce bağımsız değişkenlerini küçük harfe **dönüştürmediğinden aynı** şekilde davranır. **_mbsıcmp** ve **_mbscmp** aynı şekilde davranır, bu **_mbscmp** , bağımsız değişkenlerini karşılaştırmadan önce küçük harfe dönüştürmez.

Bu Latin 1 karakterle çalışmak için **_wcsıcmp** için [setlocale](setlocale-wsetlocale.md) çağrısı yapmanız gerekir. C yerel ayarı varsayılan olarak etkindir, bu nedenle örneğin ä, Ä ile eşit olarak karşılaştırmaz. **_Wcsıcmp**çağrısından önce C yerel ayarından başka bir yerel ayar ile **setlocale** çağrısı yapın. Aşağıdaki örnek, **_wcsıcmp** 'nin yerel ayara nasıl duyarlı olduğunu gösterir:

```C
// crt_stricmp_locale.c
#include <string.h>
#include <stdio.h>
#include <locale.h>

int main() {
   setlocale(LC_ALL,"C");   // in effect by default
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare fails
   setlocale(LC_ALL,"");
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare succeeds
}
```

Diğer bir seçenek de [_create_locale, _wcreate_locale öğesini](create-locale-wcreate-locale.md) çağırıp döndürülen yerel ayar nesnesini **_wcsicmp_l**öğesine bir parametre olarak iletmektir.

Bu işlevlerin hepsi parametrelerini doğrular. *Dize1* veya *dize2* null Işaretçilerdir, [parametre doğrulama](../../c-runtime-library/parameter-validation.md) bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **_Nlscmperror** döndürür ve **errno** öğesini **EINVAL**olarak ayarlayın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsıcmp**|**_stricmp**|**_mbsıcmp**|**_wcsıcmp**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_stricmp**, **_stricmp_l**|\<String. h >|
|**_wcsıcmp**, **_wcsicmp_l**|\<String. h > veya \<wchar. h >|
|**_mbsıcmp**, **_mbsicmp_l**|\<mbstring. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_stricmp.c

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
      strcpy_s( tmp, _countof(tmp), "less than" );
   else
      strcpy_s( tmp, _countof(tmp), "equal to" );
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );

   // Case insensitive (could use equivalent _stricmp)
   result = _stricmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof(tmp), "less than" );
   else
      strcpy_s( tmp, _countof(tmp), "equal to" );
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

[Dize düzenleme](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[_memicmp, _memicmp_l](memicmp-memicmp-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
