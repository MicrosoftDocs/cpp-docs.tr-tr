---
title: strcoll İşlevleri
ms.date: 11/04/2016
apilocation:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- strcoll
helpviewer_keywords:
- code pages, using for string comparisons
- string comparison [C++], culture-specific
- strcoll functions
- strings [C++], comparing by code page
ms.assetid: c09eeff3-8aba-4cfb-a524-752436d85573
ms.openlocfilehash: 2acfaafbe15f065dbac924ce72a5ca3a5275537b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267828"
---
# <a name="strcoll-functions"></a>strcoll İşlevleri

Her biri `strcoll` ve `wcscoll` işlevleri göre iki dizeyi karşılaştırır `LC_COLLATE` kategori ayarı yerel ayar kod sayfası şu anda kullanımda. Her biri `_mbscoll` işlevleri şu anda çok baytlı kod sayfasına göre iki dizeyi karşılaştırır. Kullanım `coll` karşılaştırması için mevcut kod sayfasında karakter kümesi sırası ve lexicographic karakter sırası arasında bir fark yoktur ve bu fark, dize karşılaştırmaları için işlevleri. Buna karşılık gelen kullanın `cmp` dize eşitlik için test etmek için işlevleri.

### <a name="strcoll-functions"></a>strcoll İşlevleri

|SBCS|Unicode|MBCS|Açıklama|
|----------|-------------|----------|-----------------|
|[strcoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[wcscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[_mbscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|İki dizeyi collate|
|[_stricoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[_wcsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[_mbsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|Collate iki dizeyi (büyük küçük harfe duyarlı)|
|[_strncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[_wcsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[_mbsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|İlk collate `count` iki dizenin karakter|
|[_strnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[_wcsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[_mbsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|İlk collate `count` (büyük-küçük harf duyarsız) iki dizenin karakter|

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin tek baytlı karakter (SBCS) sürümleri (`strcoll`, `stricoll`, `_strncoll`, ve `_strnicoll`) karşılaştırma `string1` ve `string2` göre `LC_COLLATE` geçerli yerel ayarının kategori ayarına. Bu işlevler, ilgili farklı `strcmp` , İşlevler `strcoll` işlevleri harmanlama dizileri sağlayan yerel ayar kod sayfası bilgilerini kullanın. Karakter kümesi sırası ve lexicographic karakter sırası farklı, yerel dize karşılaştırmaları için `strcoll` İşlevler, karşılık gelen yerine kullanılmalıdır `strcmp` işlevleri. Daha fazla bilgi için `LC_COLLATE`, bkz: [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).

Bazı kod sayfaları ve ilgili karakter kümeleri için karakter kümesindeki karakterlerin sırası sözlük karakter sırasından farklı olabilir. "C" yerel ayarında, bu durum geçerli değildir: ASCII karakter kümesindeki karakter sırası karakterlerin sözlük sıralamasına göre ile aynıdır. Ancak, bazı Avrupa kod sayfalarında, örneğin, karakter 'bir' (değer 0x61) karakter kümesi 'ä ''yı (değer 0xE4) karakter, karakter önündeki 'ä' önce gelen karakterin 'a' lexicographically. Böyle bir örnekte lexicographic karşılaştırmasını gerçekleştirmek için kullanın `strcoll` yerine `strcmp`. Alternatif olarak, `strxfrm` sonra özgün dizeleri kullanmak `strcmp` elde edilen dizeler.

`strcoll`, `stricoll`, `_strncoll`, ve `_strnicoll` geniş karakter (Unicode)'dekiler gibi çok baytlı karakter dizelerini şu anda kullanımda yerel ayar kod sayfasına göre otomatik olarak işler. Çok baytlı karakter (MBCS) bu işlevlerin sürümleri, ancak şu anda çok baytlı kod sayfasına göre karakter temelinde dizeler collate.

Çünkü `coll` işlevleri ise dizeleri karşılaştırma için sözlüksel olarak collate `cmp` işlevleri yalnızca dize eşitliği test `coll` işlevleri karşılık gelen daha yavaş `cmp` sürümleri. Bu nedenle, `coll` yalnızca mevcut kod sayfasında karakter kümesi sırası ve lexicographic karakter sırası arasında bir fark olduğunda ve bu fark dize karşılaştırması için ilgilendirir İşlevler'in kullanılması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[locale](../c-runtime-library/locale.md)<br/>
[Dize düzenlemesi](../c-runtime-library/string-manipulation-crt.md)<br/>
[localeconv](../c-runtime-library/reference/localeconv.md)<br/>
[_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l](../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[strcmp, wcscmp, _mbscmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)
