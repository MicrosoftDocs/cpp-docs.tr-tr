---
title: "strcoll işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords: strcoll
dev_langs: C++
helpviewer_keywords:
- code pages, using for string comparisons
- string comparison [C++], culture-specific
- strcoll functions
- strings [C++], comparing by code page
ms.assetid: c09eeff3-8aba-4cfb-a524-752436d85573
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e5f025d90d4ffac5f9dc293f621023591b5eb4f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="strcoll-functions"></a>strcoll İşlevleri
Her biri `strcoll` ve `wcscoll` işlevlerini karşılaştırılmaktadır göre iki dizeyi `LC_COLLATE` kategori ayarı yerel ayar kod sayfası şu anda kullanımda. Her biri `_mbscoll` işlevler şu anda kullanımda birden çok baytlı kod sayfasına göre iki dizeyi karşılaştırır. Kullanım `coll` işlevleri geçerli kod sayfası karakter kümesi sırasını ve lexicographic karakter sırası arasında bir fark yoktur ve bu fark karşılaştırma için ilgilendirir dize karşılaştırmaları için. Karşılık gelen kullanmak `cmp` dize eşitlik için yalnızca test etmek için işlevleri.  
  
### <a name="strcoll-functions"></a>strcoll İşlevleri  
  
|SBCS|Unicode|MBCS|Açıklama|  
|----------|-------------|----------|-----------------|  
|[strcoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[wcscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[_mbscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|İki dizeyi collate|  
|[_stricoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[_wcsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[_mbsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|Collate iki dizeyi (büyük küçük harfe duyarlı)|  
|[_strncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[_wcsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[_mbsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|İlk collate `count` iki dize karakterlerini|  
|[_strnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[_wcsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[_mbsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|İlk collate `count` iki dize (büyük küçük harf duyarsız) karakterlerini|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevler tek baytlı karakter (SBCS) sürümleri (`strcoll`, `stricoll`, `_strncoll`, ve `_strnicoll`) karşılaştırmak `string1` ve `string2` göre `LC_COLLATE` geçerli yerel kategori ayarı. Bu işlevler ilgili farklı `strcmp` , işlevlerde `strcoll` işlevlerini harmanlama sıraları sağladığı yerel ayar kod sayfası bilgileri kullanın. Dize karşılaştırmaları karakter sırasını ayarlayın ve lexicographic karakter sırası farklılık, yerel ayarlar için `strcoll` işlevleri, karşılık gelen yerine kullanılmalıdır `strcmp` işlevleri. Daha fazla bilgi için `LC_COLLATE`, bkz: [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 Bazı kod sayfaları ve karşılık gelen karakter kümesi için karakter kümesinden karakter sırasını lexicographic karakter siparişte farklı olabilir. "C" yerel ayarını durum böyle değildir: ASCII karakter kümesinden karakter sırasını karakterleri lexicographic sırasını ile aynıdır. Ancak, bazı Avrupa kod sayfalarında, örneğin, karakter 'a' (değer 0x61) karakter 'ä ''yı (değer 0xE4) karakter kümesini, karakter önündeki 'ä' önündeki karakter 'a' lexicographically. Bu tür bir örneğinde lexicographic karşılaştırma gerçekleştirmek için kullanın `strcoll` yerine `strcmp`. Alternatif olarak, kullanabileceğiniz `strxfrm` sonra özgün dizeleri kullanmak `strcmp` elde edilen dizelerde.  
  
 `strcoll`, `stricoll`, `_strncoll`, ve `_strnicoll` joker karakter (Unicode)'dekiler gibi çok baytlı karakter dizeleri şu anda kullanımda yerel ayar kod sayfası göre otomatik olarak işler. Bu işlevlerin çok baytlı karakter (MBCS) sürümleri ancak şu anda kullanımda birden çok baytlı kod sayfasına göre karakter temelinde dizeleri collate.  
  
 Çünkü `coll` işlevleri collate dizeleri karşılaştırma, lexicographically için ise `cmp` işlevleri yalnızca dize eşitlik için test `coll` işlevlerdir karşılık gelen daha çok daha yavaş `cmp` sürümleri. Bu nedenle, `coll` işlevleri yalnızca geçerli kod sayfası karakter kümesi sırasını ve lexicographic karakter sırası arasında bir fark yoktur ve bu fark dize karşılaştırma için ilgi olduğunda kullanılmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel ayar](../c-runtime-library/locale.md)   
 [Dize düzenlemesi](../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l](../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcmp, wcscmp, _mbscmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)