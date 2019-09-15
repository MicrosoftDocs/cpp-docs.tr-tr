---
title: _mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l
ms.date: 11/04/2016
api_name:
- _mbsnbicoll_l
- _mbsnbcoll_l
- _mbsnbcoll
- _mbsnbicoll
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 72c435060a6ac62213a50ba1d9fb9ef7d83fcb33
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952276"
---
# <a name="_mbsnbcoll-_mbsnbcoll_l-_mbsnbicoll-_mbsnbicoll_l"></a>_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l

Çok baytlı kod sayfası bilgilerini kullanarak iki çok baytlı karakter dizesinin *n* baytını karşılaştırır.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*biriktirme*<br/>
Karşılaştırılacak bayt sayısı.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri, *Dize1* ve *dize2*alt dizelerinin ilişkisini gösterir.

|Dönüş değeri|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* substring, *dize2* alt dizesi ile küçüktür.|
|0|*Dize1* substring, *dize2* alt dizesi ile özdeş.|
|> 0|*Dize1* substring, *dize2* alt dizinden büyük.|

*Dize1* veya *dize2* **null** ya da *Count* değeri **INT_MAX**değerinden büyükse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **_Nlscmperror** döndürür ve **errno** öğesini **EINVAL**olarak ayarlayın. **_Nlscmperror**kullanmak için String. h veya mbstring. h dahil edin.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, en çok, *Dize1* *ve* *dize2* içindeki ilk *sayı* baytlarını harmanlar ve bir değer *döndürür.* *Dize1* veya *dize2* alt dizesi içindeki son bayt bir ön bayt ise, karşılaştırmaya dahil değildir; Bu işlevler yalnızca alt dizelerdeki tüm karakterleri karşılaştırır. **_mbsnbıoll** , **_mbsnbcoll**'ın büyük/küçük harfe duyarlı bir sürümüdür. Bu şekilde, [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) ve [_mbsnbıcmp](mbsnbicmp-mbsnbicmp-l.md), **_mbsnbcoll** ve **_mbsnbıswl** gibi iki çok baytlı karakter dizesini, kullanımda olan çok baytlı [kod sayfası](../../c-runtime-library/code-pages.md) tarafından belirtilen naicographic sırasına göre Harmanla.

Bazı kod sayfaları ve karşılık gelen karakter kümeleri için, karakter kümesindeki karakterlerin sırası lexicographic karakter sıraından farklı bir şekilde değişebilir. "C" yerel ayarında bu durum böyle değildir: ASCII karakter kümesindeki karakterlerin sırası karakterlerin lexicographic sırasıyla aynıdır. Ancak, bazı Avrupa kod sayfalarında, örneğin, ' a ' karakteri (0x61) karakter kümesindeki ' ä ' (değer 0xE4) karakterinden önce gelir, ancak ' ä ' karakteri ' a ' lexıgrafik karakterinden önce gelir. Bu örnekte, dizelerin bayt olarak bir lexıgraphic karşılaştırması gerçekleştirmek için **_mbsnbcmp**yerine **_mbsnbcoll** kullanın; yalnızca dize eşitliği denetlemek için **_mbsnbcmp**kullanın.

**Coll** işlevleri karşılaştırmayı için lexıgrafik 'i karşılaştırmak üzere harmanlarken, **CMP** işlevleri yalnızca dize eşitlik için test ederken, **coll** işlevleri karşılık gelen **CMP** sürümlerinden çok daha yavaştır. Bu nedenle, **coll** işlevleri, yalnızca karakter kümesi sırası ve geçerli kod sayfasındaki lexıgraphic karakter sırası arasında bir fark olduğunda kullanılmalıdır ve bu fark karşılaştırma açısından ilgi açısından önemlidir.

Çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md) . **_L** sonekine sahip olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip sürümler, bunun yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

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
|**_mbsnbcoll**|\<mbstring. h >|
|**_mbsnbcoll_l**|\<mbstring. h >|
|**_mbsnbicoll**|\<mbstring. h >|
|**_mbsnbicoll_l**|\<mbstring. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenleme](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
