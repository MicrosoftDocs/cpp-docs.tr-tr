---
title: _strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _strncoll
- _mbsncoll_l
- _wcsncoll
- _wcsncoll_l
- _mbsncoll
- _strncoll_l
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
- mbsncoll_l
- strncoll
- _wcsncoll
- _tcsnccoll
- _ftcsnccoll
- wcsncoll
- _mbsncoll
- wcsncoll_l
- strncoll_l
- _ftcsncoll
- _strncoll
- _tcsncoll
- mbsncoll
dev_langs:
- C++
helpviewer_keywords:
- _strncoll_l function
- code pages, using for string comparisons
- _strncoll function
- _mbsncoll function
- ftcsncoll function
- strncoll function
- _ftcsncoll function
- strncoll_l function
- wcsncoll function
- mbsncoll function
- _tcsncoll function
- _tcsnccoll function
- wcsncoll_l function
- tcsnccoll function
- mbsncoll_l function
- _mbsncoll_l function
- tcsncoll function
- _wcsncoll function
- strings [C++], comparing by code page
- _ftcsnccoll function
- ftcsnccoll function
- _wcsncoll_l function
ms.assetid: e659a5a4-8afe-4033-8e72-17ffd4bdd8e9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 888484a80cc7c39921b973450afdaa361518432a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="strncoll-wcsncoll-mbsncoll-strncolll-wcsncolll-mbsncolll"></a>_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l

Yerel ayarlara özgü bilgileri kullanarak dizeleri karşılaştırır.

> [!IMPORTANT]
> **_mbsncoll** ve **_mbsncoll_l** Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _strncoll(
   const char *string1,
   const char *string2,
   size_t count
);
int _wcsncoll(
   const wchar_t *string1,
   const wchar_t *string2,
   size_t count
);
int _mbsncoll(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _strncoll_l(
   const char *string1,
   const char *string2,
   size_t count,
   _locale_t locale
);
int _wcsncoll_l(
   const wchar_t *string1,
   const wchar_t *string2,
   size_t count,
   _locale_t locale
);
int _mbsncoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Dize1*, *dize2*<br/>
Karşılaştırılacak null ile sonlandırılmış dizeler.

*Sayısı*<br/>
Karşılaştırılacak karakter sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri alt dizeler arasındaki ilişkiyi gösteren bir değer döndürür *Dize1* ve *dize2*aşağıdaki gibi.

|Dönüş değeri|Dize2 Dize1 ilişkisi|
|------------------|----------------------------------------|
|< 0|*Dize1* olan değerinden *dize2*.|
|0|*Dize1* aynıdır *dize2*.|
|> 0|*Dize1* değerinden daha büyük *dize2*.|

Bunların her biri döndürür işlevleri **_NLSCMPERROR**. Kullanılacak **_NLSCMPERROR**, STRING.h veya MBSTRING.h içerir. **_wcsncoll** ya da başarısız *Dize1* veya *dize2* harmanlama sırası etki alanının dışında olan joker karakter kodları içerir. Hata oluştuğunda **_wcsncoll** ayarlayabilir **errno** için **EINVAL**. Çağrı sırasında bir hata olup olmadığını denetlemek için **_wcsncoll**ayarlayın **errno** 0 ve denetleyin **errno** çağırdıktan sonra **_wcsncoll**.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri büyük küçük harfe duyarlı karşılaştırma ilk gerçekleştirir *sayısı* içinde karakterleri *Dize1* ve *dize2*, şu anda kullanımda kod sayfasına göre kullanın. Bu işlevler yalnızca kod sayfası karakter kümesi sırasını ve lexicographic karakter sırası arasında bir fark olduğunda ve bu fark dize karşılaştırma için ilgi olduğunda kullanın. Karakter kümesi yerel ayara bağımlı sırasıdır. Yoksa bu işlevlerin sürümleri **_l** soneki kullanım geçerli yerel ancak olan sürümleri **_l** soneki geçirilen yerel kullanın. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Tüm bu işlevlerin kendi parametreleri doğrulayın. Her iki *Dize1* veya *dize2* null işaretçinin veya *sayısı* değerinden daha büyük **INT_MAX**, geçersiz parametre işleyicisi çağrılır, bölümünde açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş **_NLSCMPERROR** ve **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnccoll**|**_strncoll**|**_mbsncoll**|**_wcsncoll**|
|**_tcsncoll**|**_strncoll**|[_mbsnbcoll](mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)|**_wcsncoll**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strncoll**, **_strncoll_l**|\<String.h >|
|**_wcsncoll**, **_wcsncoll_l**|\<wchar.h > veya \<string.h >|
|**_mbsncoll**, **_mbsncoll_l**|\<Mbstring.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[locale](../../c-runtime-library/locale.md)<br/>
[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l](mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
