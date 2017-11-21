---
title: _ismbb rutinleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _ismbb
- ismbb
dev_langs: C++
helpviewer_keywords:
- ismbb routines
- _ismbb routines
ms.assetid: d63c232e-3fe4-4844-aafd-2133846ece4b
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0f326ec0ed43463d0d2ca15103c77bb914a11592
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ismbb-routines"></a>_ismbb Rutinleri
Verilen tamsayı değeri test `c` geçerli yerel ya da belirtilen LC_CTYPE dönüştürme durumu kategori kullanarak belirli bir koşul için.  
  
|||  
|-|-|  
|[_ismbbalnum, _ismbbalnum_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|[_ismbbkprint, _ismbbkprint_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|  
|[_ismbbalpha, _ismbbalpha_l](../c-runtime-library/reference/ismbbalpha-ismbbalpha-l.md)|[_ismbbkpunct, _ismbbkpunct_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|  
|[_ismbbblank, _ismbbblank_l](../c-runtime-library/reference/ismbbblank-ismbbblank-l.md)|[_ismbblead, _ismbblead_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|  
|[_ismbbgraph, _ismbbgraph_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|[_ismbbprint, _ismbbprint_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|  
|[_ismbbkalnum, _ismbbkalnum_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|[_ismbbpunct, _ismbbpunct_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|  
|[_ismbbkana, _ismbbkana_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|[_ismbbtrail, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|  
  
## <a name="remarks"></a>Açıklamalar  
 Her yordamında `_ismbb` ailesi testleri verilen tamsayı değeri `c` belirli bir koşul için. Test sonucu yürürlükte olan birden çok baytlı kod sayfasına bağlıdır. Varsayılan olarak, birden çok baytlı kod sayfası program başlangıçta işletim sisteminden alınan ANSI kod sayfası ayarlanır. Kullanabileceğiniz [_getmbcp](../c-runtime-library/reference/getmbcp.md) kullanılmakta olan çok baytlı kod sayfası için sorgulamak üzere veya [_setmbcp](../c-runtime-library/reference/setmbcp.md) değiştirmek için.  
  
 Çıkış değerini ayarı tarafından etkilenen `LC_CTYPE` kategori ayar yerel; daha fazla bilgi için bkz. [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). Yoksa bu işlevlerin sürümleri **_l** bu yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; olan sürümleri **_l** soneki yerine bunların dışında aynı geçirilen yerel ayar parametresini kullanın.  
  
 Yordamları `_ismbb` ailesi test verilen tamsayı `c` gibi.  
  
|Yordam|Bayt test durumu|  
|-------------|-------------------------|  
|[_ismbbalnum](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|`isalnum` &#124;&#124; `_ismbbkalnum`.|  
|[_ismbbalpha](reference/ismbbalpha-ismbbalpha-l.md)|`isalpha` &#124;&#124; `_ismbbkalnum`.|  
|[_ismbbblank](../c-runtime-library/reference/ismbbblank-ismbbblank-l.md)|`isblank`|  
|[_ismbbgraph](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|Aynı `_ismbbprint`, ancak `_ismbbgraph` boşluk karakteri içermez (0x20).|  
|[_ismbbkalnum](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|Noktalama işaretleri dışında ASCII olmayan metin simge. Örneğin, yalnızca kod sayfası 932 içinde `_ismbbkalnum` katakana alfasayısal için testleri.|  
|[_ismbbkana](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|Katakana (0xA1 - 0xDF). Kod sayfası 932 özgüdür.|  
|[_ismbbkprint](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|ASCII olmayan metin veya ASCII olmayan noktalama simgesi. Örneğin, yalnızca kod sayfası 932 içinde `_ismbbkprint` katakana alfasayısal veya katakana noktalama için testler (aralık: 0xA1 - 0xDF).|  
|[_ismbbkpunct](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|ASCII olmayan noktalama işareti. Örneğin, yalnızca kod sayfası 932 içinde `_ismbbkpunct` katakana noktalama için testleri.|  
|[_ismbblead](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|Birden çok baytlı karakter ilk baytını. Örneğin, kodda 932 yalnızca, geçerli aralıklar sayfa olan 0x81 - 0x9F, 0xE0 - 0xFC.|  
|[_ismbbprint](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|`isprint` &#124;&#124; `_ismbbkprint`. **ismbbprint** boşluk karakteri içerir (0x20).|  
|[_ismbbpunct](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|`ispunct` &#124;&#124; `_ismbbkpunct`.|  
|[_ismbbtrail](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|Birden çok baytlı karakter ikinci baytı. Örneğin, kodda 932 yalnızca, geçerli aralıklar sayfa olan 0x40 - 0x7E, 0x80 - 0xEC.|  
  
 Aşağıdaki tabloda, bu yordamlar sınama koşullarını oluşturan ORed değerleri gösterir. Bildirim sabitleri `_BLANK`, `_DIGIT`, `_LOWER`, `_PUNCT`, ve `_UPPER` Ctype.h tanımlanır.  
  
|Yordam|_BLANK|_DIGIT|DAHA DÜŞÜK|_PUNCT|ÜST|Olmayan<br /><br /> ASCII<br /><br /> metin|Olmayan<br /><br /> ASCII<br /><br /> noktalama işareti|  
|-------------|-------------|-------------|-----------|-------------|-----------|------------------------------|-------------------------------|  
|`_ismbbalnum`|—|x|x|—|x|x|—|  
|`_ismbbalpha`|—|—|x|—|x|x|—|  
|`_ismbbblank`|x|—|—|—|—|—|—|  
|`_ismbbgraph`|—|x|x|x|x|x|x|  
|`_ismbbkalnum`|—|—|—|—|—|x|—|  
|`_ismbbkprint`|—|—|—|—|—|x|x|  
|`_ismbbkpunct`|—|—|—|—|—|—|x|  
|`_ismbbprint`|x|x|x|x|x|x|x|  
|`_ismbbpunct`|—|—|—|x|—|—|x|  
  
 `_ismbb` Yordamlar hem işlevleri de makroları olarak uygulanır. Ya da uygulama seçme hakkında daha fazla bilgi için bkz: [seçme arasında işlevler ve makrolar için öneriler](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bayt sınıflandırması](../c-runtime-library/byte-classification.md)   
 [is, isw rutinleri](../c-runtime-library/is-isw-routines.md)   
 [_mbbtombc, _mbbtombc_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)   
 [_mbctombb, _mbctombb_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)