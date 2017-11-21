---
title: _ismbc rutinleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords: _ismbc
dev_langs: C++
helpviewer_keywords:
- ismbc routines
- _ismbc routines
ms.assetid: b8995391-7857-4ac3-9a1e-de946eb4464d
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b512bad001ed86ad0720002cd49c54b21b6e555
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ismbc-routines"></a>_ismbc Rutinleri
Her **_ismbc** yordamı testleri belirli bir birden çok baytlı karakter `c` belirli bir koşul için.  
  
|||  
|-|-|  
|[_ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l](../c-runtime-library/reference/ismbcalnum-functions.md)|[_ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|  
|[_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l](../c-runtime-library/reference/ismbcgraph-functions.md)|[_ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|  
|[_ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|[_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|  
  
## <a name="remarks"></a>Açıklamalar  
 Her sınama sonucu **_ismbc** yordamı birden çok baytlı kod sayfasına yürürlükte bağlıdır. Çok baytlı kod sayfaları tek baytlı alfabetik karakterler var. Varsayılan olarak, birden çok baytlı kod sayfası program başlangıçta işletim sisteminden alınan sistem varsayılan ANSI kod sayfası ayarlanır. Kullanılmakta olan birden çok baytlı kod sayfasını değiştirmek veya sorguyu [_getmbcp](../c-runtime-library/reference/getmbcp.md) veya [_setmbcp](../c-runtime-library/reference/setmbcp.md)sırasıyla.  
  
 Çıkış değerini etkilenir `LC_CTYPE` yerel kategori ayarı; bkz: [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** bu yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; sürümleriyle **_l** soneki, yerel ayar parametresi kullanmasını dışında aynıdır Bunun yerine geçirildi.  
  
|Yordam|Test durumu|Kod sayfası 932 örneği|  
|-------------|--------------------|---------------------------|  
|[_ismbcalnum, _ismbcalnum_l](../c-runtime-library/reference/ismbcalnum-functions.md)|Alfasayısal|Sıfır olmayan ve yalnız döndürür `c` ASCII İngilizce harf tek baytlı gösterimidir: örnekler için bkz: `_ismbcdigit` ve `_ismbcalpha`.|  
|[_ismbcalpha, _ismbcalpha\_](../c-runtime-library/reference/ismbcalnum-functions.md)|Alfabetik|Sıfır olmayan ve yalnız döndürür `c` ASCII İngilizce harf tek baytlı gösterimidir: örnekler için bkz: `_ismbcupper` ve `_ismbclower`; veya katakana harf: 0xA6 < =`c`< 0xDF =.|  
|[_ismbcdigit, _ismbcdigit_l](../c-runtime-library/reference/ismbcalnum-functions.md)|Basamak|Sıfır olmayan ve yalnız döndürür `c` ASCII basamaklı tek baytlı gösterimidir: 0x30 < =`c`< 0x39 =.|  
|[_ismbcgraph, _ismbcgraph_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Grafiği|Sıfır olmayan ve yalnız döndürür `c` ASCII veya katakana yazdırılabilir dışında herhangi bir karakter boşluk () tek baytlı gösterimidir. Örnekler için bkz: `_ismbcdigit`, `_ismbcalpha`, ve `_ismbcpunct`.|  
|[_ismbclegal, _ismbclegal_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|Geçerli birden çok baytlı karakter|Sıfır olmayan IF ve yalnızca ilk baytı döndürür `c` 0x81-0x9F veya 0xE0 - aralıklara ikinci 0x40-0x7E veya 0x80 - aralıklara FC bayttır 0xFC, açıkken.|  
|[_ismbclower, _ismbclower_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|Küçük alfabetik|Sıfır olmayan ve yalnız döndürür `c` ASCII küçük harfli İngilizce harf tek baytlı gösterimidir: 0x61 < =`c`< 0x7A =.|  
|[_ismbcprint, _ismbcprint_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Yazdırılabilir|Sıfır olmayan ve yalnız döndürür `c` boşluk () dahil olmak üzere tüm ASCII veya katakana yazdırılabilir karakter tek baytlı gösterimidir: örnekler için bkz: `_ismbcspace`, `_ismbcdigit`, `_ismbcalpha`, ve `_ismbcpunct`.|  
|[_ismbcpunct, _ismbcpunct_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Noktalama işaretleri|Sıfır olmayan ve yalnız döndürür `c` ASCII veya katakana herhangi bir noktalama karakteri tek baytlı gösterimidir.|  
|[_ismbcblank, _ismbcblank_l,](../c-runtime-library/reference/ismbcgraph-functions.md)|Boşluk veya yatay sekme|Sıfır olmayan ve yalnız döndürür `c` bir boşluk karakteri veya yatay sekme karakteri tek baytlı gösterimidir: `c`0x20 = veya `c`0x09 =.|  
|[_ismbcspace, _ismbcspace_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Boşluk|Sıfır olmayan ve yalnız döndürür `c` bir boşluk karakteri: `c`0x20 veya 0x09 = < =`c`< = 0x0D.|  
|[_ismbcsymbol, _ismbcsymbol_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|Birden çok baytlı simgesi|Sıfır olmayan ve yalnız döndürür 0x8141 < =`c`< 0x81AC =.|  
|[_ismbcupper, _ismbcupper_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|Alfabetik büyük harf|Sıfır olmayan ve yalnız döndürür `c` ASCII büyük İngilizce harf tek baytlı gösterimidir: 0x41 < =`c`< 0x5A =.|  
  
 **Kod sayfası 932 özel**  
  
 Aşağıdaki yordamlar kod sayfası 932 özgüdür.  
  
|Yordam|(Yalnızca kod sayfası 932) koşulu test|  
|-------------|-------------------------------------------|  
|[_ismbchira, _ismbchira_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|Çift baytlık Hiragana: 0x829F < =`c`< 0x82F1 =.|  
|[_ismbckata, _ismbckata_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|Çift baytlık katakana: 0x8340 < =`c`< 0x8396 =.|  
|[_ismbcl0, _ismbcl0_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS olmayan Kanji: 0x8140 < =`c`< 0x889E =.|  
|[_ismbcl1, _ismbcl1_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS düzey 1: 0x889F < =`c`< 0x9872 =.|  
|[_ismbcl2, _ismbcl2_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS düzey 2: 0x989F < =`c`< 0xEA9E =.|  
  
 `_ismbcl0`, `_ismbcl1`, ve `_ismbcl2` denetleyin belirtilen değere `c` test koşullar açıklandığı önceki eşleşmeleri tablo, ancak, denetleme `c` geçersiz bir birden çok baytlı karakter. Alt bayt aralıkları 0x00-0x3F, 0x7F veya 0xFD - 0xFF ise, bu işlevler karakter test koşulu karşılayan gösteren sıfır olmayan bir değer döndürür. Kullanım [_ismbbtrail, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md) birden çok baytlı karakter tanımlı olup olmadığını sınamak için.  
  
 **Son kod sayfası 932 özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karakter Sınıflaması](../c-runtime-library/character-classification.md)   
 [is, isw rutinleri](../c-runtime-library/is-isw-routines.md)   
 [_ismbb rutinleri](../c-runtime-library/ismbb-routines.md)