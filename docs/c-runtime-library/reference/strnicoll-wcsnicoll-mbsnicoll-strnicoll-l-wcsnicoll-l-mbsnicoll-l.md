---
title: _strnicoll, _wcsnicoll, _mbsnicoll, _strnicoll_l, _wcsnicoll_l, _mbsnicoll_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _mbsnicoll_l
- _mbsnicoll
- _wcsnicoll_l
- _strnicoll
- _strnicoll_l
- _wcsnicoll
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
- wcshicoll_l
- _ftcsncicoll
- strnicoll_l
- _wcsnicoll
- mbsnicoll_l
- _strnicoll
- mbsnicoll
- _ftcsnicoll
- wcsnicoll
- _tcsnicoll
- _mbsnicoll
- strinicoll
- _tcsncicoll
dev_langs:
- C++
helpviewer_keywords:
- code pages, using for string comparisons
- ftcsncicoll function
- mbsnicoll_l function
- _ftcsnicoll function
- mbsnicoll function
- _tcsnicoll function
- _wcsnicoll_l function
- _mbsnicoll function
- tcsncicoll function
- strnicoll function
- _ftcsncicoll function
- wcsnicoll_l function
- _mbsnicoll_l function
- _tcsncicoll function
- strnicoll_l function
- wcsnicoll function
- _strnicoll_l function
- _wcsnicoll function
- ftcsnicoll function
- strings [C++], comparing by code page
- tcsnicoll function
- _strnicoll function
ms.assetid: abf0c569-725b-428d-9ff2-924f430104b4
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4e5c2b6bc5fb17a8f74e86d5392151c59b560e0a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="strnicoll-wcsnicoll-mbsnicoll-strnicolll-wcsnicolll-mbsnicolll"></a>_strnicoll, _wcsnicoll, _mbsnicoll, _strnicoll_l, _wcsnicoll_l, _mbsnicoll_l

Yerel ayarlara özgü bilgileri kullanarak dizeleri karşılaştırır.

> [!IMPORTANT]
> **_mbsnicoll** ve **_mbsnicoll_l** Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _strnicoll(
   const char *string1,
   const char *string2,
   size_t count
);
int _wcsnicoll(
   const wchar_t *string1,
   const wchar_t *string2 ,
   size_t count
);
int _mbsnicoll(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _strnicoll_l(
   const char *string1,
   const char *string2,
   size_t count,
   _locale_t locale
);
int _wcsnicoll_l(
   const wchar_t *string1,
   const wchar_t *string2 ,
   size_t count,
   _locale_t locale
);
int _mbsnicoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Dize1*, *dize2*<br/>
Karşılaştırılacak null ile sonlandırılmış dizeler

*Sayısı*<br/>
Karşılaştırılacak karakter sayısı

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri alt dizeler arasındaki ilişkiyi gösteren bir değer döndürür *Dize1* ve *dize2*aşağıdaki gibi.

|Dönüş değeri|Dize2 Dize1 ilişkisi|
|------------------|----------------------------------------|
|< 0|*Dize1* değerinden *dize2*|
|0|*Dize1* aynı *dize2*|
|> 0|*Dize1* büyük *dize2*|

Bunların her biri döndürür işlevleri **_NLSCMPERROR**. Kullanılacak **_NLSCMPERROR**, her iki dize içerir. H veya MBSTRING. H. **_wcsnicoll** ya da başarısız *Dize1* veya *dize2* harmanlama sırası etki alanı dışından joker karakter kodları içerir. Hata oluştuğunda **_wcsnicoll** ayarlayabilir **errno** için **EINVAL**. Çağrı sırasında bir hata olup olmadığını denetlemek için **_wcsnicoll**ayarlayın **errno** 0 ve denetleyin **errno** çağırdıktan sonra **_wcsnicoll**.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri ilk büyük küçük harf duyarsız bir karşılaştırma gerçekleştirir *sayısı* içinde karakterleri *Dize1* ve *dize2* kod sayfasına göre. Bu işlevler yalnızca, kod sayfasında sipariş ve lexicographic karakter sırası karakter arasında bir fark ayarlayabilir ve bu fark dize karşılaştırma için ilgilendirir olduğunda kullanılmalıdır. Bu işlevlerin sürümleri **_l** soneki geçerli yerel ayar ve kod sayfasını kullanın. Sürümleriyle **_l** soneki, bunun yerine geçirilen yerel ayar kullanmasını dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Tüm bu işlevlerin kendi parametreleri doğrulayın. Her iki *Dize1* veya *dize2* null işaretçinin veya sayım büyüktür **INT_MAX**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş **_NLSCMPERROR** ve **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsncicoll**|**_strnicoll**|**_mbsnbicoll**|**_wcsnicoll**|
|**_tcsnicoll**|**_strnicoll**|[_mbsnbicoll](mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)|**_wcsnicoll**|
|**_tcsnicoll_l**|**_strnicoll_l**|**_mbsnbicoll_l**|**_wcsnicoll_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strnicoll**, **_strnicoll_l**|\<String.h >|
|**_wcsnicoll**, **_wcsnicoll_l**|\<wchar.h > veya \<string.h >|
|**_mbsnicoll**, **_mbsnicoll_l**|\<Mbstring.h >|

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
