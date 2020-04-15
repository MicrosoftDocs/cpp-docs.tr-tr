---
title: strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l
ms.date: 4/2/2020
api_name:
- _mbspbrk
- wcspbrk
- _mbspbrk_l
- strpbrk
- _o__mbspbrk
- _o__mbspbrk_l
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fstrpbrk
- _mbspbrk
- strpbrk
- _tcspbrk
- _ftcspbrk
- wcspbrk
helpviewer_keywords:
- fstrpbrk function
- _ftcspbrk function
- _mbspbrk_l function
- strpbrk function
- _fstrpbrk function
- mbspbrk function
- characters [C++], scanning strings
- _tcspbrk function
- wcspbrk function
- ftcspbrk function
- character sets [C++], scanning strings for characters
- strings [C++], scanning
- tcspbrk function
- _mbspbrk function
- mbspbrk_l function
ms.assetid: 80b504f7-a167-4dde-97ad-4ae3000dc810
ms.openlocfilehash: ecdf896587096f0370351aac07cbd6be57257305
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322166"
---
# <a name="strpbrk-wcspbrk-_mbspbrk-_mbspbrk_l"></a>strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l

Belirtilen karakter kümelerinde karakterler için dizeleri tarar.

> [!IMPORTANT]
> `_mbspbrk`ve `_mbspbrk_l` Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
char *strpbrk(
   const char *str,
   const char *strCharSet
); // C only
char *strpbrk(
   char *str,
   const char *strCharSet
); // C++ only
const char *strpbrk(
   const char *str,
   const char *strCharSet
); // C++ only
wchar_t *wcspbrk(
   const wchar_t *str,
   const wchar_t *strCharSet
); // C only
wchar_t *wcspbrk(
   wchar_t *str,
   const wchar_t *strCharSet
); // C++ only
const wchar_t *wcspbrk(
   const wchar_t *str,
   const wchar_t *strCharSet
); // C++ only
unsigned char *_mbspbrk(
   const unsigned char *str,
   const unsigned char *strCharSet
); // C only
unsigned char *_mbspbrk(
   unsigned char *str,
   const unsigned char *strCharSet
); // C++ only
const unsigned char *_mbspbrk(
   const unsigned char *str,
   const unsigned char *strCharSet
); // C++ only
unsigned char *_mbspbrk_l(
   const unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
); // C only
unsigned char *_mbspbrk_l(
   unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
); // C++ only
const unsigned char *_mbspbrk_l(
   const unsigned char *str,
   const unsigned char* strCharSet,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Null-terminated, arandı dize.

*strCharSet*<br/>
Null-sonlandırılan karakter kümesi.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

*Str'deki strCharSet'ten* herhangi bir karakterin *str*ilk oluşumuna işaretçi veya iki dize bağımsız değişkeninin ortak bir karakteri yoksa NULL işaretçisi verir.

## <a name="remarks"></a>Açıklamalar

İşlev `strpbrk` *strCharSet*karakter kümesine ait *str* bir karakterin ilk oluşumu için bir işaretçi döndürür. Arama, sonlandırıcı null karakterini içermez.

`wcspbrk`ve `_mbspbrk` geniş karakterli ve çok bayt `strpbrk`karakterli versiyonlarıdır. Bağımsız `wcspbrk` değişkenler ve geri dönüş değeri geniş karakterli dizeleri; olanlar `_mbspbrk` çok bayt karakterli dizeleri vardır.

`_mbspbrk`parametrelerini doğrular. *str* veya *strCharSet* NULL ise, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmenin devam etmesine `_mbspbrk` izin verilirse, NULL döndürür ve EINVAL'e ayarlar. `errno` `strpbrk`ve `wcspbrk` parametrelerini doğrulamayın. Bu üç işlev aynı şekilde çalışır.

`_mbspbrk`bir tür `_mbscspn` `_mbspbrk` [size_t](../../c-runtime-library/standard-types.md)değeri yerine bir işaretçi döndürür dışında benzer.

C'de, bu işlevler ilk bağımsız değişken için bir **const** işaretçisi alır. C++'da iki aşırı yükleme kullanılabilir. Const için bir **const** işaretçi alarak aşırı yükleme **const**bir işaretçi döndürür; olmayan**const** bir işaretçi alır sürümü**non-const**bir işaretçi döndürür. Makro _CRT_CONST_CORRECT_OVERLOADS, bu işlevlerin **hem const** hem de**const** olmayan sürümleri varsa tanımlanır. Her iki C++ aşırı yüklemesi için**const** olmayan davranışı istiyorsanız, _CONST_RETURN simgesini tanımlayın.

Çıktı değeri, yerel LC_CTYPE kategori ayarı ayarı etkilenir; daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md)bakın. Bu işlevlerin **_l** soneki olmayan sürümleri, bu yerele bağımlı davranış için geçerli yerel durumu kullanır; **_l** soneki olan sürüm, bunun yerine geçirilen yerel parametreyi kullanması dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcspbrk`|`strpbrk`|`_mbspbrk`|`wcspbrk`|
|**Yok**|**Yok**|`_mbspbrk_l`|**Yok**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`strpbrk`|\<string.h>|
|`wcspbrk`|\<string.h> \<veya wchar.h>|
|`_mbspbrk`, `_mbspbrk_l`|\<mbstring.h>|

Uyumluluk hakkında daha fazla bilgi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_strpbrk.c

#include <string.h>
#include <stdio.h>

int main( void )
{
   char string[100] = "The 3 men and 2 boys ate 5 pigs\n";
   char *result = NULL;

   // Return pointer to first digit in "string".
   printf( "1: %s\n", string );
   result = strpbrk( string, "0123456789" );
   printf( "2: %s\n", result++ );
   result = strpbrk( result, "0123456789" );
   printf( "3: %s\n", result++ );
   result = strpbrk( result, "0123456789" );
   printf( "4: %s\n", result );
}
```

```Output
1: The 3 men and 2 boys ate 5 pigs

2: 3 men and 2 boys ate 5 pigs

3: 2 boys ate 5 pigs

4: 5 pigs
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strchr, wcschr, _mbschr, _mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
