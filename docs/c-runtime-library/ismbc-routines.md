---
title: _ismbc Rutinleri
ms.date: 11/04/2016
api_location:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ismbc
helpviewer_keywords:
- ismbc routines
- _ismbc routines
ms.assetid: b8995391-7857-4ac3-9a1e-de946eb4464d
ms.openlocfilehash: 6dc14f269cafa8ccc343c5403ab0e23d319c71c3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940162"
---
# <a name="_ismbc-routines"></a>_ismbc Rutinleri

Her bir **_ismbc** yordamı belirli bir koşul için `c` belirli bir çok baytlı karakteri sınar.

|||
|-|-|
|[_ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l](../c-runtime-library/reference/ismbcalnum-functions.md)|[_ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|
|[_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l](../c-runtime-library/reference/ismbcgraph-functions.md)|[_ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|
|[_ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|[_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|

## <a name="remarks"></a>Açıklamalar

Her bir **_ismbc** yordamının test sonucu, etkin olan çok baytlı kod sayfasına bağlıdır. Çok baytlı kod sayfalarında tek baytlık alfabetik karakterler vardır. Varsayılan olarak, çok baytlı kod sayfası, program başlangıcında işletim sisteminden alınan sistem varsayılan ANSI kod sayfasına ayarlanır. Sırasıyla [_getmbcp](../c-runtime-library/reference/getmbcp.md) veya [_setmbcp](../c-runtime-library/reference/setmbcp.md)ile kullanılan çok baytlı kod sayfasını sorgulayabilir veya değiştirebilirsiniz.

Çıkış değeri yerel ayarın `LC_CTYPE` kategori ayarından etkilenir; daha fazla bilgi için bkz. [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) . **_L** sonekine sahip olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip sürümler, bunun yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

|Yordam|Test koşulu|Kod sayfası 932 örneği|
|-------------|--------------------|---------------------------|
|[_ismbcalnum, _ismbcalnum_l](../c-runtime-library/reference/ismbcalnum-functions.md)|Sayısal|Yalnızca ASCII İngilizce harfinin tek baytlık `c` bir gösterimiyse sıfır olmayan bir değer döndürür: `_ismbcdigit` Ve`_ismbcalpha`için örneklerine bakın.|
|[_ismbcalpha, _ismbcalpha_l](../c-runtime-library/reference/ismbcalnum-functions.md)|Alfabetik|Yalnızca ASCII İngilizce harfinin tek baytlık `c` bir gösterimiyse sıfır olmayan bir değer döndürür: `_ismbcupper` Ve`_ismbclower`için örneklere bakın; veya Katakana harfi: 0xA6 < =`c`< = 0xDF.|
|[_ismbcdigit, _ismbcdigit_l](../c-runtime-library/reference/ismbcalnum-functions.md)|Gurmukhi|Yalnızca bir ASCII basamağının tek `c` baytlık bir gösterimiyse sıfır olmayan bir değer döndürür: 0x30 < =`c`< = 0x39.|
|[_ismbcgraph, _ismbcgraph_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Graphic|Yalnızca bir boşluk () dışında `c` herhangi bir ASCII veya Katakana yazılabilir karakterinin tek baytlık bir gösterimiyse sıfır olmayan bir değer döndürür. `_ismbcdigit` ,`_ismbcalpha`Ve örneklerine`_ismbcpunct`bakın.|
|[_ismbclegal, _ismbclegal_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|Geçerli çok baytlı karakter|Yalnızca ilk baytı 0x81-0x9F veya 0xE0-0xFC aralığında ise, ikinci bayt 0x40-0x7E veya 0x80-FC aralığında olduğunda sıfır olmayan bir `c` değer döndürür.|
|[_ismbclower, _ismbcalm _l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|Küçük harfli alfabetik|Yalnızca ASCII küçük harfli İngilizce harfinin `c` tek baytlık bir gösterimiyse sıfır olmayan bir değer döndürür: 0x61 < =`c`< = 0x7A.|
|[_ismbcprint, _ismbcprint_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Görüntünüzün|Yalnızca bir boşluk () dahil `c` olmak üzere herhangi bir ASCII veya Katakana yazılabilir karakterinin tek baytlık bir gösterimiyse sıfır olmayan bir değer döndürür: ,, Ve `_ismbcspace` `_ismbcdigit` için`_ismbcpunct`örneklere bakın. `_ismbcalpha`|
|[_ismbcpunct, _ismbcpunct_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Noktalama işaretleri|Yalnızca herhangi bir ASCII veya Katakana `c` noktalama karakterinin tek baytlık bir gösterimiyse sıfır olmayan bir değer döndürür.|
|[_ismbcblank, _ismbcblank_l,](../c-runtime-library/reference/ismbcgraph-functions.md)|Boşluk veya yatay sekme|Yalnızca `c` bir boşluk karakterinin veya yatay sekme karakterinin tek baytlık temsiliyse sıfır olmayan bir değer döndürür: `c`= 0x20 veya `c`= 0x09.|
|[_ismbcspace, _ismbcspace_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Boşlu|Yalnızca `c` bir boşluk karakteri ise sıfır dışında bir karakter döndürür: `c`= 0x20 veya 0x09 < =`c`< = 0x0D.|
|[_ismbcsymbol, _ismbcsymbol_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|Çok baytlı simgesi|Yalnızca 0x8141 < =`c`< = 0x81ac ise sıfır dışında bir değer döndürür.|
|[_ismbcupper, _ismbcüste_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|Büyük harfli alfabetik|Yalnızca ASCII büyük harfli İngilizce harfinin `c` tek baytlık bir gösterimiyse sıfır olmayan bir değer döndürür: 0x41 < =`c`< = 0x5A.|

**Kod sayfası 932 özgü**

Aşağıdaki yordamlar kod sayfası 932 ' e özgüdür.

|Yordam|Test koşulu (yalnızca kod sayfası 932)|
|-------------|-------------------------------------------|
|[_ismbchira, _ismbchik_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|Çift baytlık Hiragana: 0x829F < =`c`< = 0x82f1.|
|[_ismbcküta, _ismbckata_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|Çift baytlık Katakana: 0x8340 < =`c`< = 0x8396.|
|[_ismbcl0, _ismbcl0_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JıS Kanji olmayan: 0x8140 < =`c`< = 0x889e.|
|[_ismbcl1, _ismbcl1_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JıS düzey-1: 0x889F < =`c`< = 0x9872.|
|[_ismbcl2, _ismbcl2_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JıS düzey-2: 0x989F < =`c`< = 0xea9e.|

`_ismbcl0`,, ve `_ismbcl2` belirtilen değerin `c` öncekitablodaaçıklanantestkoşullarıileeşleşipeşleşmediğinikontroledin,ancakgeçerlibirçokbaytlıkarakterolduğunukontroledin.`c` `_ismbcl1` Alt bayt 0x00-0x3F, 0x7F veya 0xFD-0xFF aralıklarında bu işlevler, karakterin test koşulunu karşılayıp karşılamadığını belirten sıfır dışında bir değer döndürür. Çok baytlı karakterin tanımlanıp tanımlanmadığını test etmek için [_ismbbiz, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md) kullanın.

**Son kod sayfası 932 özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../c-runtime-library/character-classification.md)<br/>
[is, isw Yordamları](../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Yordamları](../c-runtime-library/ismbb-routines.md)
