---
title: _ismbb rutinleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
dev_langs:
- C++
helpviewer_keywords:
- ismbb routines
- _ismbb routines
ms.assetid: d63c232e-3fe4-4844-aafd-2133846ece4b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86587495353090ced63d0487991f4275d3d0d5d5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092536"
---
# <a name="ismbb-routines"></a>_ismbb Rutinleri

Belirli bir tamsayı değeri test `c` geçerli yerel ayarı veya belirtilen LC_CTYPE dönüştürme durumu kategorisini kullanarak belirli bir koşul için.

|||
|-|-|
|[_ismbbalnum, _ismbbalnum_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|[_ismbbkprint, _ismbbkprint_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|
|[_ismbbalpha, _ismbbalpha_l](../c-runtime-library/reference/ismbbalpha-ismbbalpha-l.md)|[_ismbbkpunct, _ismbbkpunct_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|
|[_ismbbblank, _ismbbblank_l](../c-runtime-library/reference/ismbbblank-ismbbblank-l.md)|[_ismbblead, _ismbblead_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|
|[_ismbbgraph, _ismbbgraph_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|[_ismbbprint, _ismbbprint_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|
|[_ismbbkalnum, _ismbbkalnum_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|[_ismbbpunct, _ismbbpunct_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|
|[_ismbbkana, _ismbbkana_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|[_ismbbtrail, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|

## <a name="remarks"></a>Açıklamalar

Her yordam, `_ismbb` ailesi testleri belirli bir tamsayı değeri `c` belirli bir koşul için. Test sonucu, geçerli çok baytlı kod sayfasına bağlıdır. Varsayılan olarak, çok baytlı kod sayfası, program başlangıcında işletim sisteminden alınan ANSI kod sayfasına ayarlanır. Kullanabileceğiniz [_getmbcp](../c-runtime-library/reference/getmbcp.md) kullanılmakta olan çok baytlı kod sayfasını sorgulamak için veya [_setmbcp](../c-runtime-library/reference/setmbcp.md) değiştirmek için.

Çıkış değeri ayarından etkilenir `LC_CTYPE` kategori ayar yerel; daha fazla bilgi için bkz. [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). Sahip olmayan bu işlevlerin sürümleri **_l** soneki geçerli yerel ayarı kullanır bu yerel ayara bağlı davranışı için; sahip sürümler **_l** sonekine yerine bunların dışında geçirilen yerel ayar parametresini kullanın.

' Ndaki yordamlara `_ismbb` ailesi test verilen tam sayıyı `c` gibi.

|Yordam|Bayt test koşulu|
|-------------|-------------------------|
|[_ismbbalnum](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|`isalnum` &#124;&#124; `_ismbbkalnum`.|
|[_ismbbalpha](reference/ismbbalpha-ismbbalpha-l.md)|`isalpha` &#124;&#124; `_ismbbkalnum`.|
|[_ismbbblank](../c-runtime-library/reference/ismbbblank-ismbbblank-l.md)|`isblank`|
|[_ismbbgraph](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|Aynı `_ismbbprint`, ancak `_ismbbgraph` boşluk karakteri dahil (0x20).|
|[_ismbbkalnum](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|Noktalama dışında ASCII olmayan metin sembolü. Örneğin, yalnızca kod sayfası 932 içinde `_ismbbkalnum` katakana alfasayısalı için test.|
|[_ismbbkana](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|Katakana (0xA1 - 0xDF). Kod sayfası 932 özel.|
|[_ismbbkprint](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|ASCII olmayan metin veya ASCII olmayan noktalama işareti sembolü. Örneğin, yalnızca kod sayfası 932 içinde `_ismbbkprint` katakana alfasayısal veya katakana noktalama için testler (aralık: 0xA1 - 0xDF).|
|[_ismbbkpunct](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|ASCII olmayan noktalama. Örneğin, yalnızca kod sayfası 932 içinde `_ismbbkpunct` katakana noktalaması için test.|
|[_ismbblead](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|Çok baytlı karakterin ilk baytı. Örneğin, kod sayfası 932 yalnızca, geçerli aralıklar olan 0x81 - 0x9F, 0xE0 - 0xFC.|
|[_ismbbprint](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|`isprint` &#124;&#124; `_ismbbkprint`. **ismbbprint** boşluk karakteri dahil (0x20).|
|[_ismbbpunct](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|`ispunct` &#124;&#124; `_ismbbkpunct`.|
|[_ismbbtrail](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|Çok baytlı karakterin ikinci baytı. Örneğin, kod sayfası 932 yalnızca, geçerli aralıklar olan 0x40 - 0x7E, 0x80 – 0xec şeklindedir.|

Aşağıdaki tabloda bu yordamlar için test koşullarını oluşturan ORed değerlerini göstermektedir. Bildirim sabitleri `_BLANK`, `_DIGIT`, `_LOWER`, `_PUNCT`, ve `_UPPER` Ctype.h içerisinde tanımlanır.

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

`_ismbb` Yordamları işlev gerekse makro olarak uygulanır. Uygulamayı seçme hakkında daha fazla bilgi için bkz. [seçme arasında işlevlerle makrolar için öneriler](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Bayt Sınıflandırması](../c-runtime-library/byte-classification.md)<br/>
[is, isw Yordamları](../c-runtime-library/is-isw-routines.md)<br/>
[_mbbtombc, _mbbtombc_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)<br/>
[_mbctombb, _mbctombb_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)