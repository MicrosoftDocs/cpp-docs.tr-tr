---
title: _ismbc Rutinleri
ms.date: 11/04/2016
apilocation:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- _ismbc
helpviewer_keywords:
- ismbc routines
- _ismbc routines
ms.assetid: b8995391-7857-4ac3-9a1e-de946eb4464d
ms.openlocfilehash: 707287ea7abe255409911f5388cd1f96d976802b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454645"
---
# <a name="ismbc-routines"></a>_ismbc Rutinleri

Her **_ismbc** rutini, belirli bir çok baytlı karakterin `c` belirli bir koşul için.

|||
|-|-|
|[_ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l](../c-runtime-library/reference/ismbcalnum-functions.md)|[_ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|
|[_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l](../c-runtime-library/reference/ismbcgraph-functions.md)|[_ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|
|[_ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|[_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|

## <a name="remarks"></a>Açıklamalar

Her test sonucu **_ismbc** yordamı çok baytlı kod sayfasına yürürlükte bağlıdır. Çok baytlı kod sayfalarında tek baytlı alfabetik karakterler vardır. Varsayılan olarak, çok baytlı kod sayfası, program başlangıcında işletim sisteminden alınan sistem varsayılan ANSI kod sayfasına ayarlanır. Sorgu veya ile kullanılan çok baytlı kod sayfasına değiştirmeniz [_getmbcp](../c-runtime-library/reference/getmbcp.md) veya [_setmbcp](../c-runtime-library/reference/setmbcp.md)sırasıyla.

Çıkış değeri tarafından etkilenen `LC_CTYPE` yerel ayarının kategori ayarına; bkz: [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** soneki geçerli yerel ayarı kullanır bu yerel ayara bağlı davranışı için; sürümleriyle **_l** sonekine bunların yerel ayar parametresini kullanmalarıdır Bunun yerine iletilmiş.

|Yordam|Test koşulu|Kod sayfası 932 örneği|
|-------------|--------------------|---------------------------|
|[_ismbcalnum, _ismbcalnum_l](../c-runtime-library/reference/ismbcalnum-functions.md)|Alfasayısal|Yalnız ve yalnızca döndürür `c` tek baytlık ASCII İngilizce harfin ise: örnekler için bkz: `_ismbcdigit` ve `_ismbcalpha`.|
|[_ismbcalpha, _ismbcalpha\_](../c-runtime-library/reference/ismbcalnum-functions.md)|Alfabetik|Yalnız ve yalnızca döndürür `c` tek baytlık ASCII İngilizce harfin ise: örnekler için bkz: `_ismbcupper` ve `_ismbclower`; veya katakana harf: 0xA6 < =`c`< 0xDF =.|
|[_ismbcdigit, _ismbcdigit_l](../c-runtime-library/reference/ismbcalnum-functions.md)|basamak|Yalnız ve yalnızca döndürür `c` tek baytlık ASCII basamak ise: 0x30 < =`c`< 0x39 =.|
|[_ismbcgraph, _ismbcgraph_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Grafiği|Yalnız ve yalnızca döndürür `c` boşluk () dışında bir ASCII veya katakana yazdırılabilir karakter tek bayt gösterimidir. Örnekler için bkz: `_ismbcdigit`, `_ismbcalpha`, ve `_ismbcpunct`.|
|[_ismbclegal, _ismbclegal_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|Geçerli çok baytlı karakter|Yalnız ve yalnızca ilk baytı döndürür `c` ikinci baytı aralıklar 0x40-0x7E veya 0x80 - FC ederken aralıklar 0x81-0x9F veya 0xE0 - 0xfc aralığında olan.|
|[_ismbclower, _ismbclower_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|Küçük harf alfabetik|Yalnız ve yalnızca döndürür `c` tek baytlık ASCII küçük harfli İngilizce harfin ise: 0x61 < =`c`< 0x7A =.|
|[_ismbcprint, _ismbcprint_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Yazdırılabilir|Yalnız ve yalnızca döndürür `c` herhangi bir karakterin boşluk () dahil olmak üzere ASCII veya katakana yazdırılabilir tek baytlık bir gösterimiyse: örnekler için bkz: `_ismbcspace`, `_ismbcdigit`, `_ismbcalpha`, ve `_ismbcpunct`.|
|[_ismbcpunct, _ismbcpunct_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Noktalama işaretleri|Yalnız ve yalnızca döndürür `c` herhangi bir ASCII veya katakana noktalama karakterinin tek baytlık gösterimidir.|
|[_ismbcblank, _ismbcblank_l,](../c-runtime-library/reference/ismbcgraph-functions.md)|Boşluk veya yatay sekme|Yalnız ve yalnızca döndürür `c` bir boşluk karakteri veya bir yatay sekme karakterinin tek baytlık bir gösterimiyse olduğu: `c`= 0x20 veya `c`= 0x09.|
|[_ismbcspace, _ismbcspace_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Boşluk|Yalnız ve yalnızca döndürür `c` bir boşluk karakteri: `c`= 0x20 veya 0x09 < =`c`< = 0x0D.|
|[_ismbcsymbol, _ismbcsymbol_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|Çok baytlı sembolü|Yalnız ve yalnızca döndürür 0x8141 < =`c`< 0x81AC =.|
|[_ismbcupper, _ismbcupper_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|Büyük alfabetik|Yalnız ve yalnızca döndürür `c` tek baytlık ASCII büyük harfli İngilizce harfin ise: 0x41 < =`c`< 0x5A =.|

**Kod sayfası 932 özel**

Aşağıdaki yordamlar kod sayfası 932'ye özeldir.

|Yordam|Test koşulu (yalnızca kod sayfası 932)|
|-------------|-------------------------------------------|
|[_ismbchira, _ismbchira_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|Çift baytlık Hiragana: 0x829F < =`c`< 0x82F1 =.|
|[_ismbckata, _ismbckata_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|Çift baytlık katakana: 0x8340 < =`c`< 0x8396 =.|
|[_ismbcl0, _ismbcl0_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS olmayan Kanji: 0x8140 < =`c`< 0x889E =.|
|[_ismbcl1, _ismbcl1_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|Düzey JIS-1: 0x889F < =`c`< 0x9872 =.|
|[_ismbcl2, _ismbcl2_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS düzey 2: 0x989F < =`c`< 0xEA9E =.|

`_ismbcl0`, `_ismbcl1`, ve `_ismbcl2` kontrol belirtilen değere `c` önceki açıklanan test koşullarıyla eşleşen tablo, ancak denetlemez `c` geçersiz bir çok baytlı karakter. Düşük bayt 0x00-0x3F, 0x7F veya 0xFD - aralıklardaki 0xFF aralıklarındaysa, bu işlevler, karakterin sınama koşulunu karşıladığını belirterek sıfır dışında bir değeri döndürür. Kullanım [_ismbbtrail, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md) çok baytlı karakterin tanımlanıp tanımlanmadığını sınamak için.

**END kod sayfası 932 özel**

## <a name="see-also"></a>Ayrıca Bkz.

[Karakter Sınıflaması](../c-runtime-library/character-classification.md)<br/>
[is, isw Yordamları](../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Yordamları](../c-runtime-library/ismbb-routines.md)