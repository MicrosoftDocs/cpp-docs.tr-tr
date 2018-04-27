---
title: strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- wcscoll
- _mbscoll
- _mbscoll_l
- strcoll
- _strcoll_l
- _wcscoll_l
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
- wcscoll
- _mbscoll
- _tcscoll
- _ftcscoll
dev_langs:
- C++
helpviewer_keywords:
- code pages, using for string comparisons
- mbscoll function
- wcscoll_l function
- ftcscoll function
- wcscoll function
- _strcoll_l function
- tcscoll function
- _ftcscoll function
- _tcscoll function
- _wcscoll_l function
- _mbscoll function
- strcoll_l function
- strcoll functions
- strings [C++], comparing by code page
ms.assetid: 900a7540-c7ec-4c2f-b292-7a85f63e3fe8
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eaddf52459ccc9af2009d04e95416d2613a5d77b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="strcoll-wcscoll-mbscoll-strcolll-wcscolll-mbscolll"></a>strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l

Geçerli yerel veya belirtilen LC_COLLATE dönüştürme durumu kategorisinin kullanarak dizeleri karşılaştırır.

> [!IMPORTANT]
> **_mbscoll** ve **_mbscoll_l** Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int strcoll(
   const char *string1,
   const char *string2
);
int wcscoll(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbscoll(
   const unsigned char *string1,
   const unsigned char *string2
);
int _strcoll_l(
   const char *string1,
   const char *string2,
   _locale_t locale
);
int wcscoll_l(
   const wchar_t *string1,
   const wchar_t *string2,
   _locale_t locale
);
int _mbscoll_l(
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

Bu işlevlerin her biri arasındaki ilişkiyi gösteren bir değer döndürür *Dize1* için *dize2*aşağıdaki gibi.

|Dönüş değeri|Dize2 Dize1 ilişkisi|
|------------------|----------------------------------------|
|< 0|*Dize1* değerinden *dize2*|
|0|*Dize1* aynı *dize2*|
|> 0|*Dize1* büyük *dize2*|

Bunların her biri döndürür işlevleri **_NLSCMPERROR** bir hata. Kullanılacak **_NLSCMPERROR**, her iki dize içerir. H veya MBSTRING. H. **wcscoll** ya da başarısız *Dize1* veya *dize2* null ya da etki alanının harmanlama sırası dışında joker karakter kodları içerir. Hata oluştuğunda **wcscoll** ayarlayabilir **errno** için **EINVAL**. Çağrı sırasında bir hata olup olmadığını denetlemek için **wcscoll**ayarlayın **errno** 0 ve denetleyin **errno** çağırdıktan sonra **wcscoll**.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri bir büyük küçük harfe duyarlı karşılaştırma gerçekleştirir *Dize1* ve *dize2* şu anda kullanımda kod sayfasına göre. Bu işlevler yalnızca, geçerli kod sayfası karakter arasında bir fark sipariş ve lexicographic karakter sırası ayarlayabilir ve bu fark dize karşılaştırma için ilgilendirir olduğunda kullanılmalıdır.

Tüm bu işlevlerin kendi parametreleri doğrulayın. Her iki *Dize1* veya *dize2* null işaretçinin veya *sayısı* değerinden daha büyük **INT_MAX**, geçersiz parametre işleyicisi çağrılır , açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş **_NLSCMPERROR** ve **errno** için **EINVAL**.

Her yerel ayar karakter sırası için farklı kurallar olduğundan, iki dizeyi karşılaştırması yerel ayara bağımlı bir işlemdir. Bu işlevlerin sürümleri **_l** sonekini kullanın Bu yerel ayara bağımlı davranış geçerli iş parçacığının yerel; sürümleriyle **_l** soneki karşılık gelen işlevi aynıdır tek fark soneki olmayan geçerli yerel yerine bir parametre olarak geçirilen yerel ayar kullanırlar. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscoll**|**strcoll**|**_mbscoll**|**wcscoll**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strcoll**|\<String.h >|
|**wcscoll**|\<wchar.h >, \<string.h >|
|**_mbscoll**, **_mbscoll_l**|\<Mbstring.h >|
|**_strcoll_l**|\<String.h >|
|**_wcscoll_l**|\<wchar.h >, \<string.h >|

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
