---
title: _strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l
ms.date: 4/2/2020
api_name:
- _strncoll
- _mbsncoll_l
- _wcsncoll
- _wcsncoll_l
- _mbsncoll
- _strncoll_l
- _o__mbsncoll
- _o__mbsncoll_l
- _o__strncoll
- _o__strncoll_l
- _o__wcsncoll
- _o__wcsncoll_l
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
ms.openlocfilehash: c9d36edde4f529651f9bed4c34b81bf977bac09f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364230"
---
# <a name="_strncoll-_wcsncoll-_mbsncoll-_strncoll_l-_wcsncoll_l-_mbsncoll_l"></a>_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l

Yerel e-özel bilgileri kullanarak dizeleri karşılaştırır.

> [!IMPORTANT]
> **_mbsncoll** ve **_mbsncoll_l,** Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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

*string1*, *string2*<br/>
Karşılaştırmak için null-sonlandırılan dizeleri.

*Sayısı*<br/>
Karşılaştırılacak karakter sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, *string1* ve *string2*alt dizeleri ilişkisini gösteren bir değer döndürür , aşağıdaki gibi.

|Döndürülen değer|String1 ile string2 arasındaki ilişki|
|------------------|----------------------------------------|
|< 0|*string1* *string2'den*daha azdır.|
|0|*string1* *string2*ile aynıdır.|
|> 0|*string1* *string2'den*büyüktür.|

Bu işlevlerin her biri **_NLSCMPERROR**döndürür. **_NLSCMPERROR**kullanmak için STRING.h veya MBSTRING.h'yi ekleyin. **string1** veya *string1* *string2,harmanlama* dizisinin etki alanı dışında geniş karakter kodları içeriyorsa _wcsncoll başarısız olabilir. Bir hata oluştuğunda, **_wcsncoll** **EINVAL** **için errno** ayarlayabilir. **_wcsncoll**için bir arama bir hata olup olmadığını kontrol etmek için, 0 **için errno** ayarlayın ve daha sonra **_wcsncoll**aradıktan sonra **errno** kontrol edin.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, şu anda kullanılmakta olan kod sayfasına göre *string1* ve *string2'deki*ilk *sayım* karakterlerinin büyük/küçük harf duyarlı bir karşılaştırmasını gerçekleştirir. Bu işlevleri yalnızca kod sayfasındaki karakter kümesi sırası ile lexicographic karakter sırası arasında bir fark olduğunda ve bu fark dize karşılaştırması için ilgi çekici olduğunda kullanın. Karakter kümesi sırası yerele bağlıdır. **_l** sonek olmayan bu işlevlerin sürümleri geçerli yerel alanı kullanır, ancak **_l** sonekolan sürümler geçirilen yerel alanı kullanır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Tüm bu işlevler parametrelerini doğrular. *String1* veya *string2* null işaretçisi ise veya *sayı* **INT_MAX**büyükse, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler **_NLSCMPERROR** döndürdü ve **EINVAL'e** **errno** ayarlayın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnccoll**|**_strncoll**|**_mbsncoll**|**_wcsncoll**|
|**_tcsncoll**|**_strncoll**|[_mbsnbcoll](mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)|**_wcsncoll**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strncoll**, **_strncoll_l**|\<string.h>|
|**_wcsncoll**, **_wcsncoll_l**|\<wchar.h> \<veya string.h>|
|**_mbsncoll**, **_mbsncoll_l**|\<mbstring.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l](mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
