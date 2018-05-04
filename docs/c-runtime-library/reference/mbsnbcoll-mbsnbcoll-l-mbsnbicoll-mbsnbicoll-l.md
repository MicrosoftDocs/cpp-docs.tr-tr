---
title: _mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsnbicoll_l
- _mbsnbcoll_l
- _mbsnbcoll
- _mbsnbicoll
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
apitype: DLLExport
f1_keywords:
- mbsnbicoll
- mbsnbcoll
- mbsnbicoll_l
- _mbsnbcoll
- _mbsnbicoll
- _ftcsnicoll
- _ftcsncoll
- mbsnbcoll_l
dev_langs:
- C++
helpviewer_keywords:
- _mbsnbcoll_l function
- mbsnbcoll_l function
- _mbsnbcoll function
- _tcsnicoll function
- mbsnbcoll function
- mbsnbicoll_l function
- mbsnbicoll function
- _tcsncoll function
- _mbsnbicoll function
- _mbsnbicoll_l function
- tcsncoll function
- tcsnicoll function
ms.assetid: d139ed63-ccba-4458-baa2-61cbcef03e94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19e17552a674d4931134eb9d7b436a0f858843d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="mbsnbcoll-mbsnbcolll-mbsnbicoll-mbsnbicolll"></a>_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l

Karşılaştırır *n* birden çok baytlı kod sayfası bilgileri kullanarak iki çok baytlı karakter dizeleri bayt.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _mbsnbcoll(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsnbcoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
int _mbsnbicoll(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsnbicoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Dize1*, *dize2*<br/>
Karşılaştırılacak dizeleri.

*Sayısı*<br/>
Karşılaştırılacak bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Alt dizeler ilişkisi dönüş değerini gösteren *Dize1* ve *dize2*.

|Dönüş değeri|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* substring değerinden *dize2* substring.|
|0|*Dize1* substring aynı *dize2* substring.|
|> 0|*Dize1* substring büyük *dize2* substring.|

Varsa *Dize1* veya *dize2* olan **NULL** veya *sayısı* değerinden daha büyük **INT_MAX**, geçersiz parametre işleyicisi çağrılır, açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş **_NLSCMPERROR** ve **errno** için **EINVAL**. Kullanılacak **_NLSCMPERROR**, String.h veya Mbstring.h içerir.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, en fazla ilk harmanlar *sayısı* bayt cinsinden *Dize1* ve *dize2* ve elde edilen arasındaki ilişkiyi gösteren bir değer döndürür alt dizeler, *Dize1* ve *dize2*. Varsa dizenin son bayt *Dize1* veya *dize2* sağlama bayt Karşılaştırmada bulunmaz; bu işlevler yalnızca tam karakterler alt dizeler karşılaştırın. **_mbsnbicoll** büyük küçük harf duyarsız bir sürümü **_mbsnbcoll**. Gibi [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) ve [_mbsnbicmp](mbsnbicmp-mbsnbicmp-l.md), **_mbsnbcoll** ve **_mbsnbicoll** göre iki çok baytlı karakter dizeleri collate çok baytlı tarafından belirtilen lexicographic düzeni [kod sayfası](../../c-runtime-library/code-pages.md) şu anda kullanımda.

Bazı kod sayfaları ve karşılık gelen karakter kümesi için karakter kümesinden karakter sırasını lexicographic karakter siparişte farklı olabilir. "C" yerel ayarını durum böyle değildir: ASCII karakter kümesinden karakter sırasını karakterleri lexicographic sırasını ile aynıdır. Ancak, bazı Avrupa kod sayfalarında, örneğin, karakter 'a' (değer 0x61) karakter 'ä ''yı (değer 0xE4) karakter kümesini, karakter önündeki 'ä' önündeki karakter 'a' lexicographically. Bu tür bir örneğini bayt tarafından dizeleri lexicographic karşılaştırması gerçekleştirmek için kullanın **_mbsnbcoll** yerine **_mbsnbcmp**; yalnızca dize eşitlik için denetleyin, kullanmak için **_mbsnbcmp**.

Çünkü **coll** işlevleri collate dizeleri karşılaştırma, lexicographically için ise **cmp** işlevleri yalnızca dize eşitlik için test **Kol** işlevleri karşılık gelen daha yavaştır **cmp** sürümleri. Bu nedenle, **Kol** işlevleri yalnızca geçerli kod sayfası karakter kümesi sırasını ve lexicographic karakter sırası arasında bir fark yoktur ve bu fark karşılaştırma için ilgi olduğunda kullanılmalıdır.

Çıkış değerini ayarı tarafından etkilenen **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** bu yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; sürümleriyle **_l** soneki, yerel ayar parametresi kullanmasını dışında aynıdır Bunun yerine geçirildi. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncoll**|[_strncoll](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|**_mbsnbcoll**|[_wcsncoll](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|
|**_tcsncoll_l**|[_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|**_mbsnbcoll_l**|[_wcsncoll_l](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|
|**_tcsnicoll**|[_strnicoll](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|**_mbsnbicoll**|[_wcsnicoll](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|
|**_tcsnicoll_l**|[_strnicoll_l](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|**_mbsnbicoll_l**|[_wcsnicoll_l](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbcoll**|\<Mbstring.h >|
|**_mbsnbcoll_l**|\<Mbstring.h >|
|**_mbsnbicoll**|\<Mbstring.h >|
|**_mbsnbicoll_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
