---
title: _ismbb Rutinleri
ms.date: 11/04/2016
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ismbb
- ismbb
helpviewer_keywords:
- ismbb routines
- _ismbb routines
ms.assetid: d63c232e-3fe4-4844-aafd-2133846ece4b
ms.openlocfilehash: b8828018040b8b6b7b13c88c08599333dc1124d0
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839380"
---
# <a name="_ismbb-routines"></a>_ismbb Rutinleri

`c`Geçerli yerel ayarı veya belirtilen LC_CTYPE dönüştürme durumu kategorisini kullanarak belirli bir koşul için verilen tamsayı değerini sınar.

:::row:::
   :::column span="":::
      [_ismbbalnum, _ismbbalnum_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)\
      [_ismbbalpha, _ismbbalpha_l](../c-runtime-library/reference/ismbbalpha-ismbbalpha-l.md)\
      [_ismbbblank, _ismbbblank_l](../c-runtime-library/reference/ismbbblank-ismbbblank-l.md)\
      [_ismbbgraph, _ismbbgraph_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)\
      [_ismbbkalnum, _ismbbkalnum_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)\
      [_ismbbkana, _ismbbkana_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)\
   :::column-end:::
   :::column span="":::
      [_ismbbkprint, _ismbbkprint_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)\
      [_ismbbkpunct, _ismbbkpunct_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)\
      [_ismbblead, _ismbblead_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)\
      [_ismbbprint, _ismbbprint_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)\
      [_ismbbpunct, _ismbbpunct_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)\
      [_ismbbtrail, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)\
   :::column-end:::
:::row-end:::

## <a name="remarks"></a>Açıklamalar

Aile içindeki her yordam `_ismbb` `c` belirli bir koşul için verilen tamsayı değerini sınar. Test sonucu, etkin olan çok baytlı kod sayfasına bağlıdır. Varsayılan olarak, çok baytlı kod sayfası, program başlangıcında işletim sisteminden elde edilen ANSI kod sayfasına ayarlanır. Kullanımda olan çok baytlı kod sayfasını sorgulamak veya değiştirmek için [_setmbcp](../c-runtime-library/reference/setmbcp.md) [_getmbcp](../c-runtime-library/reference/getmbcp.md) kullanabilirsiniz.

Çıkış değeri `LC_CTYPE` yerel ayarın kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). **_L** sonekine sahip olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip olan sürümler, bunun yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

`_ismbb`Ailedeki yordamlar verilen tamsayıyı aşağıdaki gibi test eder `c` .

|Yordam|Bayt testi koşulu|
|-------------|-------------------------|
|[_ismbbalnum](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|`isalnum` &#124;&#124; `_ismbbkalnum` .|
|[_ismbbalpha](reference/ismbbalpha-ismbbalpha-l.md)|`isalpha` &#124;&#124; `_ismbbkalnum` .|
|[_ismbbblank](../c-runtime-library/reference/ismbbblank-ismbbblank-l.md)|`isblank`|
|[_ismbbgraph](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|İle aynıdır `_ismbbprint` ancak `_ismbbgraph` boşluk karakteri (0x20) içermez.|
|[_ismbbkalnum](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|Noktalama işareti dışında ASCII olmayan metin simgesi. Örneğin, yalnızca kod sayfası 932 ' de, `_ismbbkalnum` Katakana alfasayısal için testler.|
|[_ismbbkana](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|Katakana (0xA1-0xDF). Kod sayfasına özel 932.|
|[_ismbbkprint](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|ASCII olmayan metin veya ASCII olmayan noktalama simgesi. Örneğin, yalnızca kod sayfası 932 ' de `_ismbbkprint` Katakana alfasayısal veya Katakana noktalama işaretlerini (Aralık: 0xA1-0xDF) test eder.|
|[_ismbbkpunct](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|ASCII olmayan noktalama. Örneğin, yalnızca kod sayfası 932 ' de `_ismbbkpunct` Katakana noktalama işaretlerini sınar.|
|[_ismbblead](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|Çok baytlı karakterin ilk baytı. Örneğin, yalnızca kod sayfası 932 ' de geçerli aralıklar 0x81-0x9F, 0xE0-0xFC şeklindedir.|
|[_ismbbprint](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|`isprint` &#124;&#124; `_ismbbkprint` . **ismbbprint** boşluk karakterini (0x20) içerir.|
|[_ismbbpunct](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|`ispunct` &#124;&#124; `_ismbbkpunct` .|
|[_ismbbtrail](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|Çok baytlı karakterin ikinci baytı. Örneğin, yalnızca kod sayfası 932 ' de geçerli aralıklar 0x40-0x7E, 0x80-0xEC şeklindedir.|

Aşağıdaki tabloda bu yordamlar için test koşullarını oluşturan ORed değerleri gösterilmektedir. Bildirim sabitleri,,, `_BLANK` `_DIGIT` ve, `_LOWER` `_PUNCT` `_UPPER` CType. h içinde tanımlanır.

|Yordam|_BLANK|_DIGIT|LOWER|_PUNCT|UPPER|Alınamayan<br /><br /> ASCII<br /><br /> metin|Alınamayan<br /><br /> ASCII<br /><br /> punct|
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

`_ismbb`Yordamlar hem işlev hem de makro olarak uygulanır. Her iki uygulamayı seçme hakkında daha fazla bilgi için bkz. [işlevler ve makrolar arasında seçim yapma önerileri](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt sınıflandırması](../c-runtime-library/byte-classification.md)<br/>
[, isw yordamları](../c-runtime-library/is-isw-routines.md)<br/>
[_mbbtombc, _mbbtombc_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)<br/>
[_mbctombb, _mbctombb_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)
