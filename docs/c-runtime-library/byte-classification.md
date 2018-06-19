---
title: Bayt sınıflandırması | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.types.bytes
dev_langs:
- C++
helpviewer_keywords:
- code page 932
- byte classification routines
- bytes, testing
ms.assetid: 1cb52d71-fb0c-46ca-aad7-6472c1103370
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f1051ea7b8d4cc3a3f38a5a95f015674ac3e35c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32390980"
---
# <a name="byte-classification"></a>Bayt sınıflandırması

Bu yordamlar her birden çok baytlı karakter memnuniyet bir koşul için belirtilen bayt sınar. Aksi belirtilmedikçe, çıkış değeri ayarı tarafından etkilenen dışında **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** bu yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; sürümleriyle **_l** soneki, yerel ayar parametresi kullanmasını dışında aynıdır Bunun yerine geçirildi.

> [!NOTE]
> Tanımı gereği, 0 ile 127 arasında ASCII karakterleri tüm çok baytlı karakter kümeleri bir alt kümesidir. Örneğin, ASCII olmayan karakterler yanı sıra ASCII Japonca katakana karakter kümesi içerir.

Aşağıdaki tabloda önceden tanımlanmış sabitleri tanımlanan \<ctype.h >.

## <a name="multibyte-character-byte-classification-routines"></a>Çok baytlı karakter bayt sınıflandırması yordamları

|Yordam|Bayt Test durumu|
|-------------|-------------------------|
|[isleadbyte, _isleadbyte_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|Sağlama bayt; test sonucu bağımlı **LC_CTYPE** geçerli yerel ayar kategorisi ayarı|
|[_ismbbalnum, _ismbbalnum_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|**isalnum** &#124; &#124; **_ismbbkalnum**|
|[_ismbbalpha, _ismbbalpha_l](../c-runtime-library/reference/ismbbalpha-ismbbalpha-l.md)|**isalpha** &#124; &#124; **_ismbbkalnum**|
|[_ismbbgraph, _ismbbgraph_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|Aynı **_ismbbprint**, ancak **_ismbbgraph** boşluk karakteri içermez (0x20)|
|[_ismbbkalnum, _ismbbkalnum_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|Noktalama işaretleri dışında ASCII olmayan metin simge. Örneğin, yalnızca kod sayfası 932 içinde **_ismbbkalnum** katakana alfasayısal için testleri|
|[_ismbbkana, _ismbbkana_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|Katakana (0xA1 - 0xDF), yalnızca kod sayfası 932|
|[_ismbbkprint, _ismbbkprint_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|ASCII olmayan metin veya ASCII olmayan noktalama simgesi. Örneğin, yalnızca kod sayfası 932 içinde **_ismbbkprint** katakana alfasayısal veya katakana noktalama için testler (aralık: 0xA1 - 0xDF).|
|[_ismbbkpunct, _ismbbkpunct_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|ASCII olmayan noktalama işareti. Örneğin, yalnızca kod sayfası 932 içinde **_ismbbkpunct** testleri katakana noktalama için.|
|[_ismbblead, _ismbblead_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|Birden çok baytlı karakter ilk baytını. Örneğin, kodda 932 yalnızca, geçerli aralıklar sayfa olan 0x81 - 0x9F, 0xE0 - 0xFC.|
|[_ismbbprint, _ismbbprint_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|**isprint** &#124; &#124; **_ismbbkprint**. **ismbbprint** boşluk karakteri içerir (0x20)|
|[_ismbbpunct, _ismbbpunct_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|**ispunct** &#124; &#124; **_ismbbkpunct**|
|[_ismbbtrail, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|Birden çok baytlı karakter ikinci baytı. Örneğin, kodda 932 yalnızca, geçerli aralıklar sayfa olan 0x40 - 0x7E, 0x80 - 0xEC.|
|[_ismbslead, _ismbslead_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|(String bağlamda) bayt sağlama|
|[ismbstrail, _ismbstrail_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|Sondaki (dize bağlamda) bayt|
|[_mbbtype, _mbbtype_l](../c-runtime-library/reference/mbbtype-mbbtype-l.md)|Önceki bayt üzerinde temel dönüş byte türü|
|[_mbsbtype, _mbsbtype_l](../c-runtime-library/reference/mbsbtype-mbsbtype-l.md)|Dönüş türü dizesi içinde bayt|
|[mbsinit](../c-runtime-library/reference/mbsinit.md)|Çok baytlı bir karakter dönüştürme durumunu izler.|

**MB_LEN_MAX** tanımlanan makrosu \<lımıts.h >, herhangi bir birden çok baytlı karakter olabilir bayt cinsinden en büyük uzunluğu genişletir. **MB_CUR_MAX**, içinde tanımlı \<stdlib.h >, herhangi bir birden çok baytlı karakter geçerli yerel bayt cinsinden en büyük uzunluğu genişletir.

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)