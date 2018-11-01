---
title: _stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l
ms.date: 11/04/2016
apiname:
- _mbsicoll_l
- _stricoll_l
- _mbsicoll
- _wcsicoll_l
- _wcsicoll
- _stricoll
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
- stricoll
- _stricoll
- _wcsicoll
- mbsicoll_l
- _mbsicoll
- _ftcsicoll
- wcsicoll_l
- _tcsicoll
- mbsicoll
- stricoll_l
helpviewer_keywords:
- code pages, using for string comparisons
- _ftcsicoll function
- _mbsicoll_l function
- _mbsicoll function
- mbsicoll function
- stricoll function
- tcsicoll function
- string comparison [C++], culture-specific
- _tcsicoll function
- _stricoll function
- _stricoll_l function
- _wcsicoll function
- mbsicoll_l function
- stricoll_l function
- strings [C++], comparing by code page
- ftcsicoll function
ms.assetid: 8ec93016-5a49-49d2-930f-721566661d82
ms.openlocfilehash: bd2406751fd2855afd02743c98938e530398e7d1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579679"
---
# <a name="stricoll-wcsicoll-mbsicoll-stricolll-wcsicolll-mbsicolll"></a>_stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l

Yerel ayara özgü bilgileri kullanarak dizeleri karşılaştırır.

> [!IMPORTANT]
> **_mbsicoll** ve **_mbsicoll_l** Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _stricoll(
   const char *string1,
   const char *string2
);
int _wcsicoll(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbsicoll(
   const unsigned char *string1,
   const unsigned char *string2
);
int _stricoll_l(
   const char *string1,
   const char *string2,
   _locale_t locale
);
int _wcsicoll_l(
   const wchar_t *string1,
   const wchar_t *string2,
   _locale_t locale
);
int _mbsicoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Dize1*, *dize2*<br/>
Karşılaştırmak için null ile sonlandırılmış dizeler.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri arasındaki ilişkiyi gösteren bir değer döndürür *Dize1* için *dize2*aşağıdaki gibi.

|Dönüş değeri|Dize1 dize2 ile ilişkisi|
|------------------|----------------------------------------|
|< 0|*Dize1* küçüktür *dize2*|
|0|*Dize1* aynı *dize2*|
|> 0|*Dize1* büyüktür *dize2*|
|**_NLSCMPERROR**|Bir hata oluşmuştur.|

Bu işlevlerin her biri döndürür **_NLSCMPERROR**. Kullanılacak **_NLSCMPERROR**, ya da dahil \<string.h > veya \<mbstring.h >. **_wcsicoll** ya da devredebilirsiniz *Dize1* veya *dize2* harmanlama sırasının etki alanı dışındaki geniş karakter kodlarını içerirse. Bir hata oluştuğunda **_wcsicoll** ayarlayabilir **errno** için **EINVAL**. Çağrı sırasında bir hata olup olmadığını denetlemek için **_wcsicoll**ayarlayın **errno** 0 ve **errno** arama sonra **_wcsicoll**.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri büyük küçük harf duyarsız bir karşılaştırmasını yapar *Dize1* ve *dize2* şu anda kod sayfasına göre. Bu işlevler yalnızca, geçerli kod sayfasında karakter arasında bir fark sırası ve lexicographic karakter sırası kümesi ve bu fark dize karşılaştırması için olduğunda kullanılmalıdır.

**_stricmp** farklıdır **_stricoll** bakımından **_stricmp** karşılaştırma tarafından etkilenir **LC_CTYPE**bilgileriyse **_stricoll** etkilendiği için **LC_CTYPE** ve **LC_COLLATE** yerel ayar kategorileri. Daha fazla bilgi için **LC_COLLATE** kategori bkz [setlocale](setlocale-wsetlocale.md) ve [yerel ayar kategorileri](../../c-runtime-library/locale-categories.md). Bu işlevlerin sürümleri **_l** sonekine sahip geçerli yerel ayarı kullanır; sürümleriyle **_l** soneki, bunun yerine iletilmiş yerel ayarı kullanmaları hariç, aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Bu işlevlerin tümü kendi parametrelerini doğrular. Ya da *Dize1* veya *dize2* olan **NULL** işaretçileri, geçersiz parametre işleyicisi çağrılır, açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **_NLSCMPERROR** ayarlayıp **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsicoll**|**_stricoll**|**_mbsicoll**|**_wcsicoll**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_stricoll**, **_stricoll_l**|\<String.h >|
|**_wcsicoll**, **_wcsicoll_l**|\<wchar.h >, \<string.h >|
|**_mbsicoll**, **_mbsicoll_l**|\<Mbstring.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
