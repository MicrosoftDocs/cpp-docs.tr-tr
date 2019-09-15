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
ms.openlocfilehash: 374c78ca222f9c63f6b37f26d4cf3a00f48f845e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944536"
---
# <a name="_ismbb-routines"></a>_ismbb Rutinleri

Geçerli yerel ayarı veya belirtilen `c` LC_CTYPE dönüştürme durumu kategorisini kullanarak belirli bir koşul için verilen tamsayı değerini sınar.

|||
|-|-|
|[_ismbbalnum, _ismbbalnum_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|[_ismbbkprint, _ismbbkprint_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|
|[_ismbbalpha, _ismbbalpha_l](../c-runtime-library/reference/ismbbalpha-ismbbalpha-l.md)|[_ismbbkpunct, _ismbbkpunct_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|
|[_ismbbblank, _ismbbblank_l](../c-runtime-library/reference/ismbbblank-ismbbblank-l.md)|[_ismbblead, _ismbblead_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|
|[_ismbbgraph, _ismbbgraph_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|[_ismbbprint, _ismbbprint_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|
|[_ismbbkalnum, _ismbbkalnum_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|[_ismbbpunct, _ismbbpunct_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|
|[_ismbbkana, _ismbbkana_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|[_ismbbtrail, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|

## <a name="remarks"></a>Açıklamalar

`_ismbb` Aile içindeki her yordam belirli bir koşul için verilen tamsayı `c` değerini sınar. Test sonucu, etkin olan çok baytlı kod sayfasına bağlıdır. Varsayılan olarak, çok baytlı kod sayfası, program başlangıcında işletim sisteminden elde edilen ANSI kod sayfasına ayarlanır. [_Getmbcp](../c-runtime-library/reference/getmbcp.md) 'yi, kullanımda olan çok baytlı kod sayfasını sorgulamak için veya [_setmbcp](../c-runtime-library/reference/setmbcp.md) ile değiştirmek için kullanabilirsiniz.

Çıkış değeri yerel ayarın `LC_CTYPE` kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). **_L** sonekine sahip olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip olan sürümler, bunun yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

`_ismbb` Ailedeki yordamlar verilen tamsayıyı `c` aşağıdaki gibi test eder.

|Yordam|Bayt testi koşulu|
|-------------|-------------------------|
|[_ismbbalnum](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|`isalnum` &#124;&#124; `_ismbbkalnum`.|
|[_ismbbalpha](reference/ismbbalpha-ismbbalpha-l.md)|`isalpha` &#124;&#124; `_ismbbkalnum`.|
|[_ismbbboş](../c-runtime-library/reference/ismbbblank-ismbbblank-l.md)|`isblank`|
|[_ismbbgraf](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|İle `_ismbbprint`aynıdır ancak `_ismbbgraph` boşluk karakteri (0x20) içermez.|
|[_ismbbkalnum](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|Noktalama işareti dışında ASCII olmayan metin simgesi. Örneğin, yalnızca kod sayfası 932 ' de, `_ismbbkalnum` Katakana alfasayısal için testler.|
|[_ismbbkana](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|Katakana (0xA1-0xDF). Kod sayfasına özel 932.|
|[_ismbbkyazdır](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|ASCII olmayan metin veya ASCII olmayan noktalama simgesi. Örneğin, yalnızca kod sayfası 932 ' `_ismbbkprint` de Katakana alfasayısal veya Katakana noktalama işaretlerini (Aralık: 0xA1-0xDF).|
|[_ismbbkpunct](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|ASCII olmayan noktalama. Örneğin, yalnızca kod sayfası 932 ' `_ismbbkpunct` de Katakana noktalama işaretlerini sınar.|
|[_ismbblider](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|Çok baytlı karakterin ilk baytı. Örneğin, yalnızca kod sayfası 932 ' de geçerli aralıklar 0x81-0x9F, 0xE0-0xFC şeklindedir.|
|[_ismbbprint](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|`isprint` &#124;&#124; `_ismbbkprint`. **ismbbprint** boşluk karakterini (0x20) içerir.|
|[_ismbbpunct](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|`ispunct` &#124;&#124; `_ismbbkpunct`.|
|[_ismbbiz](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|Çok baytlı karakterin ikinci baytı. Örneğin, yalnızca kod sayfası 932 ' de geçerli aralıklar 0x40-0x7E, 0x80-0xEC şeklindedir.|

Aşağıdaki tabloda bu yordamlar için test koşullarını oluşturan ORed değerleri gösterilmektedir. `_BLANK`Bildirim sabitleri `_DIGIT`,,, ve`_UPPER` , CType. h içinde tanımlanır. `_LOWER` `_PUNCT`

|Yordam|_BLANK|_BASAMAK|DÜŞÜRÜL|_PUNCT|ÜST|Alınamayan<br /><br /> ASCII<br /><br /> metin|Alınamayan<br /><br /> ASCII<br /><br /> punct|
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

`_ismbb` Yordamlar hem işlev hem de makro olarak uygulanır. Her iki uygulamayı seçme hakkında daha fazla bilgi için bkz. [işlevler ve makrolar arasında seçim yapma önerileri](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../c-runtime-library/byte-classification.md)<br/>
[is, isw Yordamları](../c-runtime-library/is-isw-routines.md)<br/>
[_mbbtombc, _mbbtombc_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)<br/>
[_mbctombb, _mbctombb_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)
