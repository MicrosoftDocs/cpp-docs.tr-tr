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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 315a86c5cf7e58219bad25f2b6633dd91275c09f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320465"
---
# <a name="_stricmp-_wcsicmp-_mbsicmp-_stricmp_l-_wcsicmp_l-_mbsicmp_l"></a>_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l

Dizeleri bir büyük/küçük harf duyarsız karşılaştırma gerçekleştirir.

> [!IMPORTANT]
> **_mbsicmp** ve **_mbsicmp_l,** Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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

*string1*, *string2*<br/>
Karşılaştırmak için null-sonlandırılan dizeleri.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

İade değeri *string1* ile *string2* arasındaki ilişkiyi aşağıdaki gibi gösterir.

|Döndürülen değer|Açıklama|
|------------------|-----------------|
|< 0|*string1* *string2'den* daha az|
|0|*string1* *string2* ile özdeş|
|> 0|*string1* *string2'den* büyük|

Bir hatada, **_mbsicmp** \<string.h> ve \<mbstring.h> tanımlanan **_NLSCMPERROR**döndürür.

## <a name="remarks"></a>Açıklamalar

**_stricmp** işlevi, her karakteri küçük harfe dönüştürdükten sonra *string1* ve *string2* ile karşılaştırır ve ilişkilerini gösteren bir değer döndürür. **_stricmp,** _stricmp **_stricoll** karşılaştırmasının **_stricmp** yalnızca **LC_CTYPE,hangi**karakterlerin daha büyük ve küçük olduğunu belirleyen _stricoll farklıdır. **_stricoll** işlevi, dizeleri hem servis talebi hem de harmanlama sırasını içeren yerel anın **LC_CTYPE** ve **LC_COLLATE** kategorilerine göre karşılaştırır. **LC_COLLATE** kategorisi hakkında daha fazla bilgi için [setyerel ve](setlocale-wsetlocale.md) [Yerel Kategoriler'e](../../c-runtime-library/locale-categories.md)bakın. Bu işlevlerin **_l** soneki olmayan sürümleri, yerel çözüme bağlı davranış için geçerli yerel alanı kullanır. Sonekli sürümler, bunun yerine geçirilen yerel liği kullanmaları dışında aynıdır. Yerel ayar ayarlanmadıysa, C yerel alanı kullanılır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

> [!NOTE]
> **_stricmp** **_strcmpi**eşdeğerdir. Bunlar birbirinin yerine kullanılabilir ancak **_stricmp** tercih edilen standarttır.

**_strcmpi** işlevi **_stricmp** eşdeğerdir ve yalnızca geriye dönük uyumluluk için sağlanır.

**_stricmp** küçük karşılaştırmalar yaptığından, beklenmeyen davranışlara neden olabilir.

**_stricmp'a** göre durum dönüştürmesinin bir karşılaştırmanın sonucunu ne zaman etkilediğini göstermek için, iki dize JOHNSTON ve JOHN_HENRY sahip olduğunuzu varsayalım. "_" küçük bir S'den daha düşük ascii değeri ne olduğundan, JOHN_HENRY dize JOHNSTON'dan daha az kabul edilir. Aslında, 91 ve 96 arasında ASCII değeri olan herhangi bir karakter herhangi bir harfdaha az kabul edilecektir.

[strcmp](strcmp-wcscmp-mbscmp.md) işlevi _stricmp yerine **kullanılırsa,** JOHN_HENRY JOHNSTON'dan büyük olacaktır.

**_wcsicmp** ve **_mbsicmp** **_stricmp**geniş karakterli ve çok bayt karakterli versiyonlarıdır. _wcsicmp bağımsız **değişkenleri** ve getiri değeri geniş karakterli dizeleridir; **_mbsicmp** çok bayt karakterli dizeleri vardır. **_mbsicmp,** geçerli çok bayt kod sayfasına göre çok bayt karakter dizilerini tanır ve bir hata üzerine **_NLSCMPERROR** döndürür. Daha fazla bilgi için [Kod Sayfaları'na](../../c-runtime-library/code-pages.md)bakın. Bu üç işlev aynı şekilde çalışır.

**_wcsicmp** ve **wcscmp** **wcscmp** onları karşılaştırmadan önce küçük harfiçin bağımsız değişkenleri dönüştürmek değil dışında aynı şekilde çalışır. **_mbsicmp** ve **_mbscmp,** **_mbscmp'nin** bağımsız değişkenlerini karşılaştırmadan önce küçük harfe dönüştürmemesi dışında aynı şekilde çalışır.

Latin 1 karakterleri ile çalışmak için **_wcsicmp** için [setlocale'yi](setlocale-wsetlocale.md) aramanız gerekir. C yerel alanı varsayılan olarak geçerli olduğundan, örneğin Ä, ğile eşit karşılaştırmaz. **_wcsicmp'a**çağrı dan önce C yerel alanı dışında herhangi bir yerel ayar ile **setlocale'yi** arayın. Aşağıdaki örnek, **_wcsicmp'ın** yerel e göre ne kadar hassas olduğunu gösterir:

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

Alternatif, _create_locale [aramak, _wcreate_locale](create-locale-wcreate-locale.md) ve **_wcsicmp_l**için bir parametre olarak döndürülen yerel nesne geçmektir.

Tüm bu işlevler parametrelerini doğrular. *String1* veya *string2* null işaretçileri ise, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md) açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler **_NLSCMPERROR** döndürdü ve **EINVAL'e** **errno** ayarlayın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsicmp**|**_stricmp**|**_mbsicmp**|**_wcsicmp**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_stricmp**, **_stricmp_l**|\<string.h>|
|**_wcsicmp**, **_wcsicmp_l**|\<string.h> \<veya wchar.h>|
|**_mbsicmp**, **_mbsicmp_l**|\<mbstring.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
