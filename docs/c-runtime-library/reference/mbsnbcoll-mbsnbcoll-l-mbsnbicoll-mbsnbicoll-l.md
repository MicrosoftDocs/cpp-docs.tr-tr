---
title: _mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l
ms.date: 4/2/2020
api_name:
- _mbsnbicoll_l
- _mbsnbcoll_l
- _mbsnbcoll
- _mbsnbicoll
- _o__mbsnbcoll
- _o__mbsnbcoll_l
- _o__mbsnbicoll
- _o__mbsnbicoll_l
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbsnbcoll
- _mbsnbcoll_l
- _mbsnbicoll
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
- _tcsncoll_l function
- _tcsnicoll_l function
ms.assetid: d139ed63-ccba-4458-baa2-61cbcef03e94
ms.openlocfilehash: 0b02a34f9b721e4cfcf07ac3679d0dce166a4ff7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340737"
---
# <a name="_mbsnbcoll-_mbsnbcoll_l-_mbsnbicoll-_mbsnbicoll_l"></a>_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l

Çok bayt kod sayfası bilgilerini kullanarak iki çok bayt karakterli dizelerin *n* baytlarını karşılaştırır.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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

*string1*, *string2*<br/>
Karşılaştırılacak dizeleri.

*Sayısı*<br/>
Karşılaştırılacak bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

İade değeri *string1* ve *string2*alt dizeleri ilişkisini gösterir.

|Döndürülen değer|Açıklama|
|------------------|-----------------|
|< 0|*string1* *string2* substring daha az substring.|
|0|*string1* substring *string2* substring ile aynıdır.|
|> 0|*string1* alt *dizestring2* substring daha büyüktür.|

*String1* veya *string2* **NULL** ise veya *sayı* **INT_MAX**büyükse, Geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler **_NLSCMPERROR** döndürdü ve **EINVAL'e** **errno** ayarlayın. **_NLSCMPERROR**kullanmak için String.h veya Mbstring.h'yi ekleyin.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, en fazla, *string1* ve string2'deki ilk *sayı* baytlarını harmlar ve *string1* ve *string2'nin* elde edilen alt dizeleri arasındaki ilişkiyi gösteren bir değer döndürür. *string2* *String1* veya *string2* alt dizesinde son bayt bir kurşun bayt ise, karşılaştırmadahil edilmez; bu işlevler yalnızca alt dizelerdeki tüm karakterleri karşılaştırır. **_mbsnbicoll** **_mbsnbcoll**bir büyük/küçük harf duyarsız sürümüdür. [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) ve [_mbsnbicmp](mbsnbicmp-mbsnbicmp-l.md)gibi, **_mbsnbcoll** ve **_mbsnbicoll** şu anda kullanılmakta olan çok bayt [kod sayfası](../../c-runtime-library/code-pages.md) tarafından belirtilen lexicographic sıraya göre iki çok bayt karakterli dizeleri harmanlayın.

Bazı kod sayfaları ve ilgili karakter kümeleri için karakter kümesindeki karakterlerin sırası lexicographic karakter sırasına göre farklılık gösterebilir. "C" tamburunda durum böyle değildir: ASCII karakter kümesindeki karakterlerin sırası, karakterlerin lexicographic sırası ile aynıdır. Ancak, bazı Avrupa kod sayfalarında, örneğin, 'a' (değer 0x61) karakteri karakter kümesindeki 'ä' (değer 0xE4) karakterinden önce gelir, ancak 'ä' karakteri 'a' lexicographically'den önce gelir. Böyle bir durumda dizelerin baytlara göre lexicographic karşılaştırmasını gerçekleştirmek **için, _mbsnbcmp**yerine **_mbsnbcoll** kullanın; yalnızca dize eşitliğini denetlemek için **_mbsnbcmp**kullanın.

Çünkü **coll** fonksiyonları karşılaştırma için dizeleri lexicographically harmanlayın, **cmp** fonksiyonları sadece dize eşitliği için test ederken, **coll** fonksiyonları karşılık gelen **cmp** sürümleri çok daha yavaştır. Bu nedenle, **coll** işlevleri yalnızca geçerli kod sayfasındakarakter kümesi sırası ile lexicographic karakter sırası arasında bir fark olduğunda kullanılmalıdır ve bu fark karşılaştırma için ilgi çekicidir.

Çıktı değeri, yerel LC_CTYPE **kategori** ayarı ayarı etkilenir; daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md) bakın. Bu işlevlerin **_l** soneki olmayan sürümleri, bu yerele bağımlı davranış için geçerli yerel durumu kullanır; **_l** soneki olan sürümler, bunun yerine geçirilen yerel parametreyi kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

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
|**_mbsnbcoll**|\<mbstring.h>|
|**_mbsnbcoll_l**|\<mbstring.h>|
|**_mbsnbicoll**|\<mbstring.h>|
|**_mbsnbicoll_l**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
