---
title: _stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l
ms.date: 4/2/2020
api_name:
- _stricmp_l
- _mbsicmp
- _wcsicmp
- _mbsicmp_l
- _stricmp
- _wcsicmp_l
- _o__mbsicmp
- _o__mbsicmp_l
- _o__stricmp
- _o__stricmp_l
- _o__wcsicmp
- _o__wcsicmp_l
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 786c2bd2738bb82b3edac5c811ccfd3f9f8bc854
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920002"
---
# <a name="_stricmp-_wcsicmp-_mbsicmp-_stricmp_l-_wcsicmp_l-_mbsicmp_l"></a>_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l

Dizelerin büyük/küçük harf duyarsız bir karşılaştırmasını yapar.

> [!IMPORTANT]
> **_mbsicmp** ve **_mbsicmp_l** , Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri, *Dize1* ile *dize2* arasındaki ilişkiyi aşağıda gösterildiği gibi gösterir.

|Döndürülen değer|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* küçüktür *dize2*|
|0|*Dize1* ile *dize2* özdeş|
|> 0|*dize2* 'den büyük *Dize1*|

Bir hatada, **_mbsicmp** String. h> ve \<mbstring. \<h> içinde tanımlanan **_NLSCMPERROR**döndürür.

## <a name="remarks"></a>Açıklamalar

**_Stricmp** işlevi, her karakteri küçük harfe dönüştürdükten sonra *Dize1* ve *dize2* 'yi karşılaştırır ve ilişkilerini gösteren bir değer döndürür. **_stricmp** , **_stricmp** karşılaştırmasının yalnızca, büyük ve küçük harfli karakterleri belirleyen **LC_CTYPE**tarafından etkilendiğinden **_stricoll** farklıdır. **_Stricoll** işlevi, hem durumu hem de harmanlama sırasını içeren yerel ayarların **LC_CTYPE** ve **LC_COLLATE** kategorilerine göre dizeleri karşılaştırır. **LC_COLLATE** kategorisi hakkında daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md) ve [locale kategorileri](../../c-runtime-library/locale-categories.md). **_L** soneki olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. Sonekine sahip sürümler, bunun yerine geçirilen yerel ayarı kullanmaları dışında aynıdır. Yerel ayar ayarlanmamışsa, C yerel ayarı kullanılır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

> [!NOTE]
> **_stricmp** **_strcmpi**eşdeğerdir. Bunlar birbirinin yerine kullanılabilirler, ancak **_stricmp** tercih edilen standarttır.

**_Strcmpi** işlevi **_stricmp** eşdeğerdir ve yalnızca geriye dönük uyumluluk için sağlanır.

**_Stricmp** küçük harf karşılaştırmaları yaptığından, beklenmeyen davranışlara neden olabilir.

Büyük/küçük harf dönüştürmenin **_stricmp** bir karşılaştırmanın sonucunu etkilediği zaman göstermek için, iki DIZININ JOHNSTON ve JOHN_HENRY olduğunu varsayalım. "_" Küçük harfli bir ASCII değerine sahip olduğu için dize JOHN_HENRY, JOHNSTON 'tan daha az kabul edilir. Aslında, 91 ve 96 arasında bir ASCII değeri olan herhangi bir karakter herhangi bir harften daha az kabul edilir.

**_Stricmp**yerine [strcmp](strcmp-wcscmp-mbscmp.md) IşLEVI kullanılırsa JOHN_HENRY, Johnston 'den büyük olur.

**_wcsicmp** ve **_mbsicmp** , **_stricmp**geniş karakter ve çok baytlı karakter sürümleridir. **_Wcsicmp** bağımsız değişkenleri ve dönüş değeri geniş karakterli dizelerdir; **_mbsicmp** olanlar çok baytlı karakter dizeleridir. **_mbsicmp** , geçerli çok baytlı kod sayfasına göre çok baytlı karakter dizilerini tanır ve bir hata üzerinde **_NLSCMPERROR** döndürür. Daha fazla bilgi için bkz. [kod sayfaları](../../c-runtime-library/code-pages.md). Bu üç işlev, aynı şekilde davranır.

**_wcsicmp** ve **wcscmp** aynı şekilde davranır. bu **wcscmp** , bağımsız değişkenlerini karşılaştırmadan önce küçük harfe dönüştürmez. **_mbsicmp** ve **_mbscmp** , **_mbscmp** bağımsız değişkenlerini karşılaştırmadan önce küçük harfe dönüştürmediğinden aynı şekilde davranır.

**_Wcsicmp** için [setlocale](setlocale-wsetlocale.md) 'i çağırmanız gerekir ve bu Latin 1 karakterle çalışır. C yerel ayarı varsayılan olarak etkindir, bu nedenle örneğin ä, Ä ile eşit olarak karşılaştırmaz. **_Wcsicmp**çağrısından önce C yerel ayarından başka bir yerel ayar ile **setlocale** çağrısı yapın. Aşağıdaki örnek, **_wcsicmp** yerel ayara nasıl duyarlı olduğunu gösterir:

```C
// crt_stricmp_locale.c
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

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

Diğer bir seçenek de [_wcreate_locale _create_locale](create-locale-wcreate-locale.md) çağrısı yapmak ve döndürülen yerel ayar nesnesini **_wcsicmp_l**bir parametre olarak iletmektir.

Bu işlevlerin hepsi parametrelerini doğrular. *Dize1* veya *dize2* null Işaretçilerdir, [parametre doğrulama](../../c-runtime-library/parameter-validation.md) bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **_NLSCMPERROR** döndürür ve **errno** , **EINVAL**olarak ayarlanır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsicmp**|**_stricmp**|**_mbsicmp**|**_wcsicmp**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_stricmp**, **_stricmp_l**|\<String. h>|
|**_wcsicmp**, **_wcsicmp_l**|\<String. h> veya \<wchar. h>|
|**_mbsicmp**, **_mbsicmp_l**|\<mbstring. h>|

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

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[_memicmp, _memicmp_l](memicmp-memicmp-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
