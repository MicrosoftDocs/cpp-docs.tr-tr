---
title: _stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _stricmp_l
- _mbsicmp
- _wcsicmp
- _mbsicmp_l
- _stricmp
- _wcsicmp_l
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0014ea3c727db2a368123696c47df1eca6ba3bb4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418334"
---
# <a name="stricmp-wcsicmp-mbsicmp-stricmpl-wcsicmpl-mbsicmpl"></a>_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l

Dizeleri büyük küçük harf duyarsız bir karşılaştırma gerçekleştirir.

> [!IMPORTANT]
> **_mbsicmp** ve **_mbsicmp_l** Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri ilişkisi gösterir *Dize1* için *dize2* gibi.

|Dönüş değeri|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* değerinden *dize2*|
|0|*Dize1* aynı *dize2*|
|> 0|*Dize1* büyük *dize2*|

Bir hata **_mbsicmp** döndürür **_NLSCMPERROR**, içinde tanımlanan \<string.h > ve \<mbstring.h >.

## <a name="remarks"></a>Açıklamalar

**_Stricmp** işlev ordinally karşılaştırır *Dize1* ve *dize2* ilişkilerini gösteren bir değer küçük ve döndürür her karakter dönüştürme sonra. **_stricmp** farklıdır **_stricoll** bakımından **_stricmp** karşılaştırma tarafından etkilenen yalnızca **LC_CTYPE**, hangi karakter üst belirler ve küçük harf. **_Stricoll** işlevi karşılaştırır dizeleri hem göre **LC_CTYPE** ve **LC_COLLATE** durum ve harmanlama içeren yerel ayar kategorileri sırası. Hakkında daha fazla bilgi için **LC_COLLATE** kategorisi, bkz: [setlocale](setlocale-wsetlocale.md) ve [yerel ayar kategorileri](../../c-runtime-library/locale-categories.md). Bu işlevlerin sürümleri **_l** soneki geçerli yerel ayar için yerel ayara bağımlı davranışı kullanın. Bunun yerine geçirilen yerel ayar kullanmasını dışında soneki sürümleriyle aynıdır. Yerel ayar ayarlı değil, C yerel ayar kullanılır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

> [!NOTE]
> **_stricmp** eşdeğerdir **_strcmpi**. Birbirinin yerine kullanılabilir ancak **_stricmp** tercih edilen standardıdır.

**_Strcmpi** işlevi eşdeğerdir **_stricmp** ve yalnızca geriye dönük uyumluluk için sağlanır.

Çünkü **_stricmp** karşılaştırmaları, küçük harf beklenmeyen davranışlara neden olabilir.

Ne zaman göstermeye durumda dönüştürme **_stricmp** sonucu etkiler karşılaştırması, iki dizeyi JOHNSTON ve JOHN_HENRY olduğunu varsayın. JOHNSTON değerinden JOHN_HENRY olarak kabul edilmelidir dizesi "_" küçük S. daha düşük bir ASCII değer içerdiğinden Aslında, ASCII değeri 91 96 arasındaki sahip herhangi bir karakter değerinden herhangi bir harf kabul edilir.

Varsa [strcmp](strcmp-wcscmp-mbscmp.md) işlevi yerine kullanılır **_stricmp**, JOHN_HENRY JOHNSTON büyük olacaktır.

**_wcsicmp** ve **_mbsicmp** joker karakter ve çok baytlı karakter sürümleri **_stricmp**. Bağımsız değişkenleri ve dönüş değerini **_wcsicmp** joker karakter olan dizeleri; bu **_mbsicmp** çok baytlı karakter dizeleri belirtilmiştir. **_mbsicmp** geçerli birden çok baytlı kod sayfasına göre çok baytlı karakter sıralarının tanır ve döndürür **_NLSCMPERROR** bir hata. Daha fazla bilgi için bkz: [kod sayfaları](../../c-runtime-library/code-pages.md). Bu üç işlevler aynı şekilde aksi davranır.

**_wcsicmp** ve **wcscmp** durumlar dışında aynı şekilde davranır **wcscmp** karşılaştırılmadan önce küçük bağımsız değişkenlerini dönüştürmez. **_mbsicmp** ve **_mbscmp** durumlar dışında aynı şekilde davranır **_mbscmp** karşılaştırılmadan önce küçük bağımsız değişkenlerini dönüştürmez.

Çağırmanız gerekir [setlocale](setlocale-wsetlocale.md) için **_wcsicmp** Latin 1 karakter ile çalışmak için. C yerel ayar yürürlükte varsayılan olarak, bu nedenle, örneğin, ä Ä eşit karşılaştırmak değil'dır. Çağrı **setlocale** çağırmadan önce C yerel dışında herhangi bir yerel ayarı ile **_wcsicmp**. Aşağıdaki örnek gösterilmektedir nasıl **_wcsicmp** yerel duyarlıdır:

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

Alternatif çağırmaktır [_create_locale, _wcreate_locale](create-locale-wcreate-locale.md) ve döndürülen yerel ayar nesnesini parametre olarak geçirmek **_wcsicmp_l**.

Tüm bu işlevlerin kendi parametreleri doğrulayın. Her iki *Dize1* veya *dize2* null işaretçiler açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş **_NLSCMPERROR** ve **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsicmp**|**_stricmp**|**_mbsicmp**|**_wcsicmp**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_stricmp**, **_stricmp_l**|\<String.h >|
|**_wcsicmp**, **_wcsicmp_l**|\<String.h > veya \<wchar.h >|
|**_mbsicmp**, **_mbsicmp_l**|\<Mbstring.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[_memicmp, _memicmp_l](memicmp-memicmp-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
