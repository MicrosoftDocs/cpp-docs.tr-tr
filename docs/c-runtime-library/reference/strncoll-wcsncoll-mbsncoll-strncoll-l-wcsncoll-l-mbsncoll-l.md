---
title: _strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l
ms.date: 11/04/2016
api_name:
- _strncoll
- _mbsncoll_l
- _wcsncoll
- _wcsncoll_l
- _mbsncoll
- _strncoll_l
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
ms.openlocfilehash: e5120b37cd06266752194ec826a173474f6902fd
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70947259"
---
# <a name="_strncoll-_wcsncoll-_mbsncoll-_strncoll_l-_wcsncoll_l-_mbsncoll_l"></a>_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l

Yerel ayara özgü bilgileri kullanarak dizeleri karşılaştırır.

> [!IMPORTANT]
> **_mbsncoll** ve **_mbsncoll_l** Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*biriktirme*<br/>
Karşılaştırılacak karakter sayısı.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, aşağıdaki gibi, *Dize1* ve *dize2*alt dizelerinin ilişkisini gösteren bir değer döndürür.

|Dönüş değeri|Dize1 ile dize2 arasındaki ilişki|
|------------------|----------------------------------------|
|< 0|*Dize1* *dize2*'den küçük.|
|0|*Dize1* , *dize2*ile aynıdır.|
|> 0|*Dize1* *dize2*'den büyük.|

Bu işlevlerin her biri **_Nlscmperror**döndürür. **_Nlscmperror**kullanmak için STRING. h veya mbstring. h dahil edin. **_wcsncoll** , bir *Dize1* ya da *dize2* , harmanlama sırasının etki alanı dışındaki geniş karakter kodları içeriyorsa başarısız olabilir. Bir hata oluştuğunda, **_wcsncoll** , **errno** 'u **EINVAL**olarak ayarlayabilir. **_Wcsncoll**çağrısında bir hata olup olmadığını denetlemek için **errno** ' ı 0 olarak ayarlayın ve ardından **_wcsncoll**öğesini çağırdıktan sonra **errno** ' u denetleyin.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, şu anda kullanımda olan kod sayfasına göre *Dize1* ve *dize2*içindeki ilk *sayı* karakterlerinin büyük küçük harfe duyarlı bir karşılaştırmasını yapar. Bu işlevleri yalnızca, kod sayfasındaki karakter kümesi sırası ve lexicographic karakter sırası arasında bir fark olduğunda ve bu fark, dize karşılaştırması için ne zaman ilgilendiği durumlarda kullanın. Karakter kümesi sırası, yerel ayara bağımlıdır. **_L** sonekine sahip olmayan bu işlevlerin sürümleri, geçerli yerel ayarı kullanır, ancak **_l** sonekine sahip sürümler geçirilen yerel ayarı kullanır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Bu işlevlerin hepsi parametrelerini doğrular. *Dize1* veya *dize2* , null bir Işaretçiyse veya *sayı* **INT_MAX**değerinden büyükse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **_Nlscmperror** döndürür ve **errno** öğesini **EINVAL**olarak ayarlayın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnccoll**|**_strncoll**|**_mbsncoll**|**_wcsncoll**|
|**_tcsncoll**|**_strncoll**|[_mbsnbcoll](mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)|**_wcsncoll**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strncoll**, **_strncoll_l**|\<String. h >|
|**_wcsncoll**, **_wcsncoll_l**|\<wchar. h > veya \<String. h >|
|**_mbsncoll**, **_mbsncoll_l**|\<mbstring. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[locale](../../c-runtime-library/locale.md)<br/>
[Dize düzenleme](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l](mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
