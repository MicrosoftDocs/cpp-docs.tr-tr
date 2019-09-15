---
title: strcoll İşlevleri
ms.date: 11/04/2016
api_location:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- strcoll
helpviewer_keywords:
- code pages, using for string comparisons
- string comparison [C++], culture-specific
- strcoll functions
- strings [C++], comparing by code page
ms.assetid: c09eeff3-8aba-4cfb-a524-752436d85573
ms.openlocfilehash: c63a130cee6913006fff2ed5568c41cc4fdeac3c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944894"
---
# <a name="strcoll-functions"></a>strcoll İşlevleri

Ve `strcoll` `LC_COLLATE` işlevlerinin her biri, şu anda kullanımda olan yerel ayar kodu sayfasının kategori ayarına göre iki dizeyi karşılaştırır. `wcscoll` `_mbscoll` İşlevlerin her biri, şu anda kullanımda olan çok baytlı kod sayfasına göre iki dizeyi karşılaştırır. Geçerli kod sayfasındaki karakter kümesi sırası ve lexicographic karakter sırası arasında bir fark olduğunda dize karşılaştırmaları için işlevlerikullanınvebufarkkarşılaştırmaaçısındanilginin.`coll` Yalnızca dize eşitlik `cmp` için test etmek üzere ilgili işlevleri kullanın.

### <a name="strcoll-functions"></a>strcoll İşlevleri

|SBCS|Unicode|MBCS|Açıklama|
|----------|-------------|----------|-----------------|
|[strcoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[wcscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[_mbscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|İki dizeyi harmanlama|
|[_stricoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[_wcsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[_mbsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|İki dizeyi Harmanla (büyük/küçük harfe duyarsız)|
|[_strncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[_wcsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[_mbsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|İki dizenin `count` ilk karakterlerini Harmanla|
|[_strnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[_wcsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[_mbsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|İki dizenin `count` ilk karakterini Harmanla (büyük/küçük harf duyarsız)|

## <a name="remarks"></a>Açıklamalar

`strcoll`Bu işlevlerin (, `stricoll`, `_strncoll` `string1` ve `_strnicoll`) tek baytlı karakter (SBCS) sürümleri, geçerli yerel ayarın `LC_COLLATE` kategori ayarına `string2` göre karşılaştırılır. Bu işlevler, `strcoll` işlevlerin harmanlama dizileri `strcmp` sağlayan yerel ayar kod sayfası bilgilerini kullanmasına karşılık gelen işlevlerden farklıdır. Karakter kümesi sırası ve lexicographic karakter sırasının farklı olduğu yerel ayarlarda dize karşılaştırmaları için, `strcoll` işlevler karşılık gelen `strcmp` işlevler yerine kullanılmalıdır. Hakkında `LC_COLLATE`daha fazla bilgi için bkz. [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).

Bazı kod sayfaları ve karşılık gelen karakter kümeleri için, karakter kümesindeki karakterlerin sırası lexicographic karakter sıraından farklı olabilir. "C" yerel ayarında bu durum böyle değildir: ASCII karakter kümesindeki karakterlerin sırası karakterlerin lexicographic sırasıyla aynıdır. Ancak, bazı Avrupa kod sayfalarında, örneğin, ' a ' karakteri (0x61) karakter kümesindeki ' ä ' (değer 0xE4) karakterinden önce gelir, ancak ' ä ' karakteri ' a ' lexıgrafik karakterinden önce gelir. Böyle bir örnek içinde bir lexıgraphic karşılaştırması gerçekleştirmek için `strcoll` `strcmp`yerine kullanın. Alternatif olarak, `strxfrm` özgün dizeler üzerinde öğesini kullanabilir ve sonra elde edilen `strcmp` dizeler üzerinde kullanabilirsiniz.

`strcoll`,,, ve`_strnicoll` çok baytlı karakter dizelerini kullanımda olan yerel ayar kodu sayfasına göre otomatik olarak işler, geniş karakter (Unicode) karşılıklarına `stricoll`göre. `_strncoll` Bununla birlikte, bu işlevlerin çok baytlı karakter (MBCS) sürümleri, kullanılmakta olan çok baytlı kod sayfasına göre dizeleri bir karakter temelinde harmanler.

İşlevler, dizeleri karşılaştırma için bir şekilde harmanladı, `cmp` ancak işlevler dize eşitlik `coll` için test ederken, işlevler karşılık gelen `cmp` sürümlerden çok daha yavaştır. `coll` Bu nedenle, `coll` işlevleri yalnızca, geçerli kod sayfasında karakter kümesi sırası ve lexicographic karakter sırası arasında bir fark olduğunda kullanılmalıdır ve bu fark dize karşılaştırması için ilginin.

## <a name="see-also"></a>Ayrıca bkz.

[locale](../c-runtime-library/locale.md)<br/>
[Dize düzenleme](../c-runtime-library/string-manipulation-crt.md)<br/>
[localeconv](../c-runtime-library/reference/localeconv.md)<br/>
[_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l](../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[strcmp, wcscmp, _mbscmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)
