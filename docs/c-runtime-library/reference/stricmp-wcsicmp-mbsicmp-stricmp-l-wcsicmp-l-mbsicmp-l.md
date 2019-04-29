---
title: _stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l
ms.date: 11/04/2016
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
ms.openlocfilehash: d27b2128d79d7ff3ab0150e182d494fed52d46ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353846"
---
# <a name="stricmp-wcsicmp-mbsicmp-stricmpl-wcsicmpl-mbsicmpl"></a>_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l

Dizeler büyük küçük harf duyarsız bir karşılaştırma gerçekleştirir.

> [!IMPORTANT]
> **_mbsicmp** ve **_mbsicmp_l** Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Karşılaştırmak için null ile sonlandırılmış dizeler.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri ilişkisi gösterir *Dize1* için *dize2* gibi.

|Dönüş değeri|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* küçüktür *dize2*|
|0|*Dize1* aynı *dize2*|
|> 0|*Dize1* büyüktür *dize2*|

Bir hatada **_mbsicmp** döndürür **_NLSCMPERROR**, tanımlanan \<string.h > ve \<mbstring.h >.

## <a name="remarks"></a>Açıklamalar

**_Stricmp** işlev ordinally karşılaştırır *Dize1* ve *dize2* sonra her bir karakteri küçük ve döndürür dönüştürme ilişkilerini gösteren bir değer. **_stricmp** farklıdır **_stricoll** bakımından **_stricmp** karşılaştırma tarafından etkilenen yalnızca **LC_CTYPE**, hangi karakter üst belirler ve küçük harfler içermeli. **_Stricoll** işlevi hem de göre dizeleri karşılaştırır **LC_CTYPE** ve **LC_COLLATE** hem durum hem de harmanlama içeren yerel ayar kategorileri sırası. Hakkında daha fazla bilgi için **LC_COLLATE** kategori bkz [setlocale](setlocale-wsetlocale.md) ve [yerel ayar kategorileri](../../c-runtime-library/locale-categories.md). Bu işlevlerin sürümleri **_l** soneki, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. Sonekine sahip sürümler, bunun yerine iletilmiş yerel ayarı kullanmaları dışında aynıdır. Yerel ayar ayarlı değil, C yerel ayarı kullanılır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

> [!NOTE]
> **_stricmp** eşdeğerdir **_strcmpi**. Bunlar birbirlerinin yerine kullanılabilir fakat **_stricmp** tercih edilen standart'tır.

**_Strcmpi** işlev, eşdeğer **_stricmp** ve yalnızca geriye dönük uyumluluk için sağlanır.

Çünkü **_stricmp** karşılaştırmalar, küçük harf beklenmeyen davranışlara neden olabilir.

Ne zaman göstermek için servis talebi dönüştürme **_stricmp** sonucu etkiler karşılaştırması, iki dizeyi JOHNSTON ve JOHN_HENRY sahip olduğunuzu varsaymaktadır. JOHNSTON değerinden JOHN_HENRY değerlendirilir dize "_", bir küçük harf S. daha düşük bir ASCII değer olduğundan Aslında, 91 96 arasındaki ASCII değeri olan herhangi bir karakterle az harf kabul edilir.

Varsa [strcmp](strcmp-wcscmp-mbscmp.md) işlevi yerine kullanılır **_stricmp**, JOHN_HENRY JOHNSTON büyük olacaktır.

**_wcsicmp** ve **_mbsicmp** geniş karakter ve çok baytlı karakter sürümleridir **_stricmp**. Bağımsız değişkenler ve dönüş değeri **_wcsicmp** geniş karakterli dizelerdir; **_mbsicmp** çok baytlı karakter dizeleridir. **_mbsicmp** geçerli çok baytlı kod sayfasına göre çok baytlı karakter dizileri tanır ve döndürür **_NLSCMPERROR** üzerinde hata. Daha fazla bilgi için [kod sayfaları](../../c-runtime-library/code-pages.md). Bu üç işlev aynı şekilde davranır.

**_wcsicmp** ve **wcscmp** aynı şekilde davranır **wcscmp** karşılaştırmadan önce küçük, bağımsız değişkenlerinin dönüştürmez. **_mbsicmp** ve **_mbscmp** aynı şekilde davranır **_mbscmp** karşılaştırmadan önce küçük, bağımsız değişkenlerinin dönüştürmez.

Çağırmak ihtiyacınız olacak [setlocale](setlocale-wsetlocale.md) için **_wcsicmp** Latin 1 karakter ile çalışmak için. C yerel uygulamada varsayılan olarak, bu nedenle, örneğin, ä Ä eşit karşılaştırma değil olur. Çağrı **setlocale** çağırmadan önce C yerel ayarı dışındaki herhangi bir yerel ayar ile **_wcsicmp**. Aşağıdaki örnekte nasıl **_wcsicmp** yerel duyarlıdır:

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

Çağrılacak alternatiftir [_create_locale, _wcreate_locale](create-locale-wcreate-locale.md) ve döndürülen yerel ayar nesnesini parametre olarak geçirmek **_wcsicmp_l**.

Bu işlevlerin tümü kendi parametrelerini doğrular. Ya da *Dize1* veya *dize2* null işaretçiler açıklandığı gibi geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **_NLSCMPERROR** ayarlayıp **errno** için **EINVAL**.

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
