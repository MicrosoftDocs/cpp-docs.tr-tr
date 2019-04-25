---
title: _mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l
ms.date: 11/04/2016
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
ms.openlocfilehash: c18faa3c93969a683b3ee3ef58dd02e1c1ae61f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156726"
---
# <a name="mbsnbcoll-mbsnbcolll-mbsnbicoll-mbsnbicolll"></a>_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l

Karşılaştırır *n* çok baytlı kod sayfası bilgilerini kullanarak iki çok baytlı karakterli dizenin bayt.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Karşılaştırılacak dizeler.

*Sayısı*<br/>
Karşılaştırılacak bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri dizelerinin ilişkisini gösteren *Dize1* ve *dize2*.

|Dönüş değeri|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* alt dize küçüktür *dize2* alt dize.|
|0|*Dize1* aynı alt dizeyi *dize2* alt dize.|
|> 0|*Dize1* alt dizeyi büyük *dize2* alt dize.|

Varsa *Dize1* veya *dize2* olduğu **NULL** veya *sayısı* büyüktür **INT_MAX**, geçersiz parametre işleyicisi çağrılır, açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **_NLSCMPERROR** ayarlayıp **errno** için **EINVAL**. Kullanılacak **_NLSCMPERROR**, STRING.h veya Mbstrıng.h ekleyin.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, en çok ilk harmanlar *sayısı* bayt cinsinden *Dize1* ve *dize2* ve ortaya çıkan arasındaki ilişkiyi gösteren bir değer döndürür alt dizeler *Dize1* ve *dize2*. Varsa alt dizesindeki son bayt *Dize1* veya *dize2* bir müşteri adayı bayt karşılaştırmaya eklenmez; bu işlevler yalnızca Dizelerdeki tam karakterleri karşılaştırır. **_mbsnbicoll** büyük küçük harf duyarlı bir sürümüdür **_mbsnbcoll**. Gibi [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) ve [_mbsnbicmp](mbsnbicmp-mbsnbicmp-l.md), **_mbsnbcoll** ve **_mbsnbicoll** göre iki çok baytlı karakter dizelerini collate çok baytlı tarafından belirtilen sözlük sıralamasına göre [kod sayfası](../../c-runtime-library/code-pages.md) şu anda kullanımda.

Bazı kod sayfaları ve ilgili karakter kümeleri için karakter kümesindeki karakterlerin sırası sözlük karakter sırasından farklı olabilir. "C" yerel ayarında, bu durum geçerli değildir: ASCII karakter kümesindeki karakter sırası karakterlerin sözlük sıralamasına göre ile aynıdır. Ancak, bazı Avrupa kod sayfalarında, örneğin, karakter 'bir' (değer 0x61) karakter kümesi 'ä ''yı (değer 0xE4) karakter, karakter önündeki 'ä' önce gelen karakterin 'a' lexicographically. Bu tür bir örnek bayt tarafından dizeleri lexicographic karşılaştırmasını gerçekleştirmek için **_mbsnbcoll** yerine **_mbsnbcmp**; yalnızca dize eşitliği kontrolü, kullanın **_mbsnbcmp**.

Çünkü **coll** işlevleri ise dizeleri karşılaştırma için sözlüksel olarak collate **cmp** işlevleri yalnızca dize eşitliği test **coll** işlevleri Buna karşılık gelen daha yavaştır **cmp** sürümleri. Bu nedenle, **coll** yalnızca mevcut kod sayfasında karakter kümesi sırası ve lexicographic karakter sırası arasında bir fark olduğunda ve bu fark karşılaştırması için İşlevler'in kullanılması gerekir.

Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** soneki geçerli yerel ayarı kullanır bu yerel ayara bağlı davranışı için; sürümleriyle **_l** sonekine bunların yerel ayar parametresini kullanmalarıdır Bunun yerine iletilmiş. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

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

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
