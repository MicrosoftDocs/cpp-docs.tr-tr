---
description: 'Daha fazla bilgi edinin: bayt sınıflandırması'
title: Bayt sınıflandırması
ms.date: 04/04/2018
f1_keywords:
- c.types.bytes
helpviewer_keywords:
- code page 932
- byte classification routines
- bytes, testing
ms.assetid: 1cb52d71-fb0c-46ca-aad7-6472c1103370
ms.openlocfilehash: 00691ca85366c5cbbe28b023f2a269838128fe9e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221702"
---
# <a name="byte-classification"></a>Bayt sınıflandırması

Bu yordamların her biri, bir koşulun memnuniyet açısından çok baytlı bir karakterin belirtilen baytını sınar. Aksi belirtilmedikçe, çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) . **_L** soneki olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip sürümler, bunun yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

> [!NOTE]
> Tanım olarak, 0 ve 127 arasındaki ASCII karakterleri, çok baytlı karakter kümelerinin bir alt kümesidir. Örneğin, Japonca katakana karakter kümesi ASCII ve ASCII olmayan karakterler içerir.

Aşağıdaki tabloda önceden tanımlanmış sabitler ' de tanımlanmıştır \<ctype.h> .

## <a name="multibyte-character-byte-classification-routines"></a>Çok baytlı karakter bayt-sınıflandırma yordamları

|Yordam|Bayt testi koşulu|
|-------------|-------------------------|
|[isleadbyte, _isleadbyte_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|Ön bayt; test sonucu, geçerli yerel ayarın **LC_CTYPE** kategori ayarına bağlıdır|
|[_ismbbalnum, _ismbbalnum_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|**isalnum** &#124;&#124; **_ismbbkalnum**|
|[_ismbbalpha, _ismbbalpha_l](../c-runtime-library/reference/ismbbalpha-ismbbalpha-l.md)|**isalpha** &#124;&#124; **_ismbbkalnum**|
|[_ismbbgraph, _ismbbgraph_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|**_İsmbbprint** ile aynıdır, ancak **_ismbbgraph** boşluk karakterini içermez (0x20)|
|[_ismbbkalnum, _ismbbkalnum_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|Noktalama işareti dışında ASCII olmayan metin simgesi. Örneğin, yalnızca kod sayfası 932 ' de, Katakana alfasayısal için **_ismbbkalnum** testleri|
|[_ismbbkana, _ismbbkana_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|Katakana (0xA1-0xDF), yalnızca kod sayfası 932|
|[_ismbbkprint, _ismbbkprint_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|ASCII olmayan metin veya ASCII olmayan noktalama simgesi. Örneğin, yalnızca kod sayfası 932 ' de Katakana alfasayısal veya Katakana noktalama (Aralık: 0xA1-0xDF) için testler **_ismbbkprint** .|
|[_ismbbkpunct, _ismbbkpunct_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|ASCII olmayan noktalama. Örneğin, yalnızca kod sayfası 932 ' de Katakana noktalama işaretlerini **_ismbbkpunct** .|
|[_ismbblead, _ismbblead_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|Çok baytlı karakterin ilk baytı. Örneğin, yalnızca kod sayfası 932 ' de geçerli aralıklar 0x81-0x9F, 0xE0-0xFC şeklindedir.|
|[_ismbbprint, _ismbbprint_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|**isprint** &#124;&#124; **_ismbbkprint**. **ismbbprint** boşluk karakterini içerir (0x20)|
|[_ismbbpunct, _ismbbpunct_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|**ispunct** &#124;&#124; **_ismbbkpunct**|
|[_ismbbtrail, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|Çok baytlı karakterin ikinci baytı. Örneğin, yalnızca kod sayfası 932 ' de geçerli aralıklar 0x40-0x7E, 0x80-0xEC şeklindedir.|
|[_ismbslead, _ismbslead_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|Ön bayt (dize bağlamında)|
|[ismbstraıl, _ismbstrail_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|Sondaki bayt (dize bağlamında)|
|[_mbbtype, _mbbtype_l](../c-runtime-library/reference/mbbtype-mbbtype-l.md)|Önceki bayta göre bayt türü döndür|
|[_mbsbtype, _mbsbtype_l](../c-runtime-library/reference/mbsbtype-mbsbtype-l.md)|Dize içindeki baytın dönüş türü|
|[mbsinit](../c-runtime-library/reference/mbsinit.md)|Çok baytlı bir karakter dönüştürme durumunu izler.|

İçinde tanımlanan **MB_LEN_MAX** makrosu, \<limits.h> herhangi bir çok baytlı karakterin sahip olduğu en fazla uzunluğu bayt olarak genişletir. İçinde tanımlanan **MB_CUR_MAX**, \<stdlib.h> geçerli yerel ayarda bulunan çok baytlı bir karakterin bayt olarak en fazla uzunluğuna genişletilir.

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)
