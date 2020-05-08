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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: f75bf4bb28a2dc34a233374314e6bc170793d77e
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920368"
---
# <a name="strcoll-wcscoll-_mbscoll-_strcoll_l-_wcscoll_l-_mbscoll_l"></a>strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l

Geçerli yerel ayarı veya belirtilen LC_COLLATE dönüştürme durumu kategorisini kullanarak dizeleri karşılaştırır.

> [!IMPORTANT]
> **_mbscoll** ve **_mbscoll_l** , Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, aşağıdaki gibi, *Dize1* to *dize2*arasındaki ilişkiyi gösteren bir değer döndürür.

|Döndürülen değer|Dize1 ile dize2 arasındaki ilişki|
|------------------|----------------------------------------|
|< 0|*Dize1* küçüktür *dize2*|
|0|*Dize1* ile *dize2* özdeş|
|> 0|*dize2* 'den büyük *Dize1*|

Bu işlevlerin her biri hata **_NLSCMPERROR** döndürür. **_NLSCMPERROR**kullanmak için, her iki dizeyi de ekleyin. H veya MBSTRING. Olsun. **wcscoll** , *Dize1* veya *dize2* **null** ise veya harmanlama sırasının etki alanı dışındaki geniş karakter kodlarını içerirse başarısız olabilir. Bir hata oluştuğunda, **wcscoll** **errno** 'u **EINVAL**olarak ayarlayabilir. **Wcscoll**çağrısında bir hata olup olmadığını denetlemek için **errno** ' ı 0 olarak ayarlayın ve ardından **wcscoll**çağrıldıktan sonra **errno** ' u denetleyin.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, şu anda kullanımda olan kod sayfasına göre *Dize1* ve *dize2* 'nin büyük küçük harfe duyarlı bir karşılaştırmasını yapar. Bu işlevler yalnızca, geçerli kod sayfasındaki karakter kümesi sırası ve lexicographic karakter sırası arasında bir fark olduğunda ve bu fark dize karşılaştırmasının farklılığı olduğunda kullanılmalıdır.

Bu işlevlerin hepsi parametrelerini doğrular. *Dize1* veya *dize2* , null bir işaretçiyse veya *sayı* **INT_MAX**büyükse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md) bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **_NLSCMPERROR** döndürür ve **errno** , **EINVAL**olarak ayarlanır.

Her yerel ayarın karakterleri sıralamak için farklı kurallara sahip olduğundan, iki dizenin karşılaştırılması yerel ayara bağlı bir işlemdir. **_L** soneki olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli iş parçacığının yerel ayarını kullanır; **_l** sonekine sahip sürümler, geçerli yerel ayar yerine bir parametre olarak geçirilen yerel ayarı kullanmaları dışında, karşılık gelen işlevle birlikte ilgili işlevle aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscoll**|**strcoll**|**_mbscoll**|**wcscoll**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strcoll**|\<String. h>|
|**wcscoll**|\<wchar. h>, \<String. h>|
|**_mbscoll**, **_mbscoll_l**|\<mbstring. h>|
|**_strcoll_l**|\<String. h>|
|**_wcscoll_l**|\<wchar. h>, \<String. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Ayarlar](../../c-runtime-library/locale.md)<br/>
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
