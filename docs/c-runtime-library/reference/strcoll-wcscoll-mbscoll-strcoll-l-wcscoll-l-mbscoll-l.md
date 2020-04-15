---
title: strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l
ms.date: 4/2/2020
api_name:
- wcscoll
- _mbscoll
- _mbscoll_l
- strcoll
- _strcoll_l
- _wcscoll_l
- _o__mbscoll
- _o__mbscoll_l
- _o__strcoll_l
- _o__wcscoll_l
- _o_strcoll
- _o_wcscoll
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
- wcscoll
- _mbscoll
- _tcscoll
- _ftcscoll
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
ms.openlocfilehash: 9cbf24fafa78ac6a53a99abf0d1bb1ab3a0625c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358122"
---
# <a name="strcoll-wcscoll-_mbscoll-_strcoll_l-_wcscoll_l-_mbscoll_l"></a>strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l

Geçerli yerel alanı veya belirli bir LC_COLLATE dönüşüm durumu kategorisini kullanarak dizeleri karşılaştırır.

> [!IMPORTANT]
> **_mbscoll** ve **_mbscoll_l,** Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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

*string1*, *string2*<br/>
Karşılaştırmak için null-sonlandırılan dizeleri.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri *string1* ile *string2*arasındaki ilişkiyi gösteren bir değer döndürür , aşağıdaki gibi.

|Döndürülen değer|String1 ile string2 arasındaki ilişki|
|------------------|----------------------------------------|
|< 0|*string1* *string2'den* daha az|
|0|*string1* *string2* ile özdeş|
|> 0|*string1* *string2'den* büyük|

Bu işlevlerin her biri bir hata **_NLSCMPERROR** döndürür. **_NLSCMPERROR**kullanmak için, string içerir. H veya MBSTRING. H. *string1* veya *string2* **NULL** ise veya harmanlama dizisinin etki alanı dışında geniş karakter kodları içeriyorsa **wcscoll** başarısız olabilir. Bir hata oluştuğunda, **wcscoll** **Errno'u EINVAL**olarak ayarlayabilir. **errno** **wcscoll**bir çağrı bir hata olup olmadığını kontrol etmek için , 0 **errno** ayarlayın ve sonra **wcscoll**aradıktan sonra **errno** kontrol edin.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, şu anda kullanılmakta olan kod sayfasına göre *string1* ve *string2'nin* büyük/küçük harf duyarlı bir karşılaştırmasını gerçekleştirir. Bu işlevler yalnızca geçerli kod sayfasındaki karakter kümesi sırası ile lexicographic karakter sırası arasında bir fark olduğunda kullanılmalıdır ve bu fark dize karşılaştırması için ilgi çekicidir.

Tüm bu işlevler parametrelerini doğrular. *String1* veya *string2* null işaretçisi ise veya *sayı* **INT_MAX**büyükse, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md) açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler **_NLSCMPERROR** döndürdü ve **EINVAL'e** **errno** ayarlayın.

Her yerel yerin karakter sıralamak için farklı kuralları olduğundan, iki dizenin karşılaştırılması yerel e-bağımlı bir işlemdir. Bu işlevlerin **_l** sonek olmayan sürümleri, bu yerelliğe bağımlı davranış için geçerli iş parçacığının yerelsini kullanır; **_l** soneki olan sürümler, geçerli yerel alan yerine parametre olarak geçirilen yerelliği kullanmaları dışında, sonek olmadan karşılık gelen işlek ile aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscoll**|**strcoll**|**_mbscoll**|**wcscoll**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strcoll**|\<string.h>|
|**wcscoll**|\<wchar.h>, \<string.h>|
|**_mbscoll**, **_mbscoll_l**|\<mbstring.h>|
|**_strcoll_l**|\<string.h>|
|**_wcscoll_l**|\<wchar.h>, \<string.h>|

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
