---
title: _strnset_s, _strnset_s_l, _wcsnset_s, _wcsnset_s_l, _mbsnset_s, _mbsnset_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsnset_s_l
- _strnset_s
- _mbsnset_s
- _strnset_s_l
- _wcsnset_s_l
- _wcsnset_s
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
- _mbsnset_s_l
- wcsnset_s
- _tcsnset_s_l
- _wcsnset_s
- _mbsnset_s
- _wcsnset_s_l
- _strnset_s_l
- strnset_s_l
- _tcsnset_s
- _strnset_s
- strnset_s
- mbsnset_s_l
- mbsnset_s
- wcsnset_s_l
dev_langs:
- C++
helpviewer_keywords:
- tcsnset_s function
- mbsnset_s_l function
- initializing characters
- wcsnset_s function
- mbsnset_s function
- _tcsnset_s_l function
- _strnset_s_l function
- _mbsnset_s function
- strnset_s_l function
- _tcsnset_s function
- _strnset_s function
- tcsnset_s_l function
- _mbsnset_s_l function
- strnset_s function
- _wcsnset_s function
ms.assetid: 9cf1b321-b5cb-4469-b285-4c07cfbd8813
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 786f802a25964b118b997a2d5af7376932f8f74f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="strnsets-strnsetsl-wcsnsets-wcsnsetsl-mbsnsets-mbsnsetsl"></a>_strnset_s, _strnset_s_l, _wcsnset_s, _wcsnset_s_l, _mbsnset_s, _mbsnset_s_l

Belirli bir karakter dizesine karakterlerinden başlatır. Bu sürümleri [_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> **_mbsnset_s** ve **_mbsnset_s_l** Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _strnset_s(
   char *str,
   size_t numberOfElements,
   int c,
   size_t count
);
errno_t _strnset_s_l(
   char *str,
   size_t numberOfElements,
   int c,
   size_t count,
   locale_t locale
);
errno_t _wcsnset_s(
   wchar_t *str,
   size_t numberOfElements,
   wchar_t c,
   size_t count
);
errno_t _wcsnset_s_l(
   wchar_t *str,
   size_t numberOfElements,
   wchar_t c,
   size_t count,
   _locale_t locale
);
errno_t _mbsnset_s(
   unsigned char *str,
   size_t numberOfElements,
   unsigned int c,
   size_t count
);
errno_t _mbsnset_s_l(
   unsigned char *str,
   size_t numberOfElements,
   unsigned int c,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Değiştirilecek dize.

*numberOfElements*<br/>
Boyutunu *str* arabellek.

*c*<br/>
Karakter değeri.

*Sayısı*<br/>
Ayarlanacak karakter sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, sıfır Aksi takdirde bir hata kodu.

Bu işlevler kendi bağımsız değişkenleri doğrulayın. Varsa *str* null ile sonlandırılmış geçerli bir dize değil veya geçersiz parametre işleyicisi çağrıldıktan sonra boyutu bağımsız değişkeniyle 0 ' değerinden küçük veya eşit açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için bu işlevler dönüş bir hata kodu ve kümesi yürütülmesine izin veriliyorsa **errno** bu hata kodu. Varsayılan hata kodu **EINVAL** daha belirli bir değerin geçerli olmadığında.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, en fazla ilk kümesinden *sayısı* karakterlerinden *str* için *c*. Varsa *sayısı* boyutundan daha büyük *str*, boyutu *str* yerine kullanılan *sayısı*. Bir hata oluşur *sayısı* değerinden daha büyük *numberOfElements* ve bu parametrelerinin her ikisini de boyutundan büyük olan *str*.

**_wcsnset_s** ve **_mbsnset_s** joker karakter ve çok baytlı karakter sürümleri **_strnset_s**. Dize bağımsız değişkeni **_wcsnset_s** geniş karakter dizesi;'ın **_mbsnset_s** amultibyte karakter dizesidir. Bu üç işlevler aynı şekilde aksi davranır.

Çıkış değerini ayarı tarafından etkilenen **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** bu yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; sürümleriyle **_l** soneki, yerel ayar parametresi kullanmasını dışında aynıdır Bunun yerine geçirildi. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Bu işlevler hata ayıklama sürümleri ilk 0xFD arabellekle doldurun. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnset_s**|**_strnset_s**|**_mbsnbset_s**|**_wcsnset_s**|
|**_tcsnset_s_l**|**_strnset_s_l**|**_mbsnbset_s_l**|**_wcsnset_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strnset_s**|\<String.h >|
|**_strnset_s_l**|\<Tchar.h >|
|**_wcsnset_s**|\<String.h > veya \<wchar.h >|
|**_wcsnset_s_l**|\<Tchar.h >|
|**_mbsnset_s**, **_mbsnset_s_l**|\<Mbstring.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_strnset_s.c
#include <string.h>
#include <stdio.h>

int main( void )
{
   char string[15] = "This is a test";
   /* Set not more than 4 characters of string to be *'s */
   printf( "Before: %s\n", string );
   _strnset_s( string, sizeof(string), '*', 4 );
   printf( "After:  %s\n", string );
}
```

```Output
Before: This is a test
After:  **** is a test
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
