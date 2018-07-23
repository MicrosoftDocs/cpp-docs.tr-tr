---
title: strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbspbrk
- wcspbrk
- _mbspbrk_l
- strpbrk
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
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fstrpbrk
- _mbspbrk
- strpbrk
- _tcspbrk
- _ftcspbrk
- wcspbrk
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db26c60badceab6c1422146a32de3d6dd2ecb8bd
ms.sourcegitcommit: 04d327940787df1297b72d534f388a035d472af0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39181139"
---
# <a name="strpbrk-wcspbrk-mbspbrk-mbspbrkl"></a>strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l

Belirtilen karakter kümelerindeki karakterler için dizeleri tarar.

> [!IMPORTANT]
> `_mbspbrk` ve `_mbspbrk_l` Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*str*<br/>
Null ile sonlandırılmış, aranan dize.

*strCharSet*<br/>
Null ile sonlandırılmış karakter kümesi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Herhangi bir karakterin ilk geçtiği yere bir işaretçi döndürür *strCharSet* içinde *str*, ya da iki dize bağımsız değişkenleri, bir NULL işaretçi herhangi bir karakter ortak sahip.

## <a name="remarks"></a>Açıklamalar

`strpbrk` İşlevi, bir karakterin ilk geçtiği yere bir işaretçi döndürür *str* karakter kümesine ait olan *strCharSet*. Arama, sonlandırıcı null karakteri içermez.

`wcspbrk` ve `_mbspbrk` geniş karakter ve çok baytlı karakter sürümleridir `strpbrk`. Bağımsız değişkenler ve dönüş değeri `wcspbrk` geniş karakterli dizelerdir; `_mbspbrk` çok baytlı karakter dizeleridir.

`_mbspbrk` kendi parametrelerini doğrular. Varsa *str* veya *strCharSet* NULL ise açıklandığı gibi geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse `_mbspbrk` NULL döndürür ve ayarlar `errno` EINVAL için. `strpbrk` ve `wcspbrk` kendi parametrelerini doğrulamazlar. Bu üç işlev aynı şekilde davranır.

`_mbspbrk` benzer `_mbscspn` dışında `_mbspbrk` türünde bir değer yerine bir işaretçi döndürür [size_t](../../c-runtime-library/standard-types.md).

C'de bu işlevler alır bir **const** ilk bağımsız değişken için bir işaretçi. C++'da, iki aşırı yüklemesi kullanılabilir. Bir işaretçi alan aşırı yükleme **const** bir işaretçi döndürür **const**; olmayan bir işaretçiye alan sürüm**const** olmayan bir işaretçi döndürür**const** . Her iki makro _CRT_CONST_CORRECT_OVERLOADS tanımlanan **const** ve olmayan-**const** bu işlevlerin sürümleri mevcuttur. Olmayan gerektiriyorsa**const** davranışı için her iki C++ aşırı _const_return sembolünü.

Çıkış değeri yerel LC_CTYPE kategori ayarı ayarından etkilenir; Daha fazla bilgi için [setlocale](setlocale-wsetlocale.md). Bu işlevlerin sürümleri **_l** soneki geçerli yerel ayarı kullanır bu yerel ayara bağlı davranışı için; sürümü ile **_l** soneki, yerel ayar parametresini kullanması hariç, aynıdır Bunun yerine iletilmiş. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcspbrk`|`strpbrk`|`_mbspbrk`|`wcspbrk`|
|**yok**|**yok**|`_mbspbrk_l`|**yok**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`strpbrk`|\<String.h >|
|`wcspbrk`|\<String.h > veya \<wchar.h >|
|`_mbspbrk`, `_mbspbrk_l`|\<Mbstring.h >|

Uyumluluk hakkında daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strchr, wcschr, _mbschr, _mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
