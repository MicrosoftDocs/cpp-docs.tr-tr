---
title: Bayt sınıflandırması
ms.date: 04/04/2018
f1_keywords:
- c.types.bytes
helpviewer_keywords:
- code page 932
- byte classification routines
- bytes, testing
ms.assetid: 1cb52d71-fb0c-46ca-aad7-6472c1103370
ms.openlocfilehash: 9c00d0c0165bdae15ba5fc413d00a99bf4601b21
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632407"
---
# <a name="byte-classification"></a>Bayt sınıflandırması

Bu yordamların her biri koşula uyması için çok baytlı bir karakterin belirtilen bir bayt sınar. Aksi belirtilmedikçe, çıkış değeri ayarından etkilenir dışında **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** soneki geçerli yerel ayarı kullanır bu yerel ayara bağlı davranışı için; sürümleriyle **_l** sonekine bunların yerel ayar parametresini kullanmalarıdır Bunun yerine iletilmiş.

> [!NOTE]
> Tanımı gereği, 0 ve 127 arasındaki ASCII karakter tüm çok baytlı karakter kümelerinin alt kümesidir. Örneğin, Japonca katakana karakter kümesi, ASCII ve bunun yanı sıra ASCII olmayan karakterler de içerir.

Önceden tanımlanmış sabitleri aşağıdaki tabloda tanımlanan \<ctype.h >.

## <a name="multibyte-character-byte-classification-routines"></a>Çok baytlı karakter bayt-sınıflandırma rutinleri

|Yordam|Bayt Test koşulu|
|-------------|-------------------------|
|[isleadbyte, _isleadbyte_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|Müşteri adayı bayt; test sonucu bağlıdır **LC_CTYPE** geçerli yerel ayar kategori ayarı|
|[_ismbbalnum, _ismbbalnum_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|**isalnum** &#124; &#124; **_ismbbkalnum**|
|[_ismbbalpha, _ismbbalpha_l](../c-runtime-library/reference/ismbbalpha-ismbbalpha-l.md)|**isalpha** &#124; &#124; **_ismbbkalnum**|
|[_ismbbgraph, _ismbbgraph_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|Aynı **_ismbbprint**, ancak **_ismbbgraph** boşluk karakteri dahil (0x20)|
|[_ismbbkalnum, _ismbbkalnum_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|Noktalama dışında ASCII olmayan metin sembolü. Örneğin, yalnızca kod sayfası 932 içinde **_ismbbkalnum** katakana alfasayısalı için test|
|[_ismbbkana, _ismbbkana_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|Katakana (0xA1 - 0xDF), yalnızca kod sayfası 932|
|[_ismbbkprint, _ismbbkprint_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|ASCII olmayan metin veya ASCII olmayan noktalama işareti sembolü. Örneğin, yalnızca kod sayfası 932 içinde **_ismbbkprint** katakana alfasayısal veya katakana noktalama için testler (aralık: 0xA1 - 0xDF).|
|[_ismbbkpunct, _ismbbkpunct_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|ASCII olmayan noktalama. Örneğin, yalnızca kod sayfası 932 içinde **_ismbbkpunct** katakana noktalaması için test.|
|[_ismbblead, _ismbblead_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|Çok baytlı karakterin ilk baytı. Örneğin, kod sayfası 932 yalnızca, geçerli aralıklar olan 0x81 - 0x9F, 0xE0 - 0xFC.|
|[_ismbbprint, _ismbbprint_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|**isprint** &#124; &#124; **_ismbbkprint**. **ismbbprint** boşluk karakteri dahil (0x20)|
|[_ismbbpunct, _ismbbpunct_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|**ispunct** &#124; &#124; **_ismbbkpunct**|
|[_ismbbtrail, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|Çok baytlı karakterin ikinci baytı. Örneğin, kod sayfası 932 yalnızca, geçerli aralıklar olan 0x40 - 0x7E, 0x80 – 0xec şeklindedir.|
|[_ismbslead, _ismbslead_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|Müşteri adayı bayt (bağlamında dize)|
|[ismbstrail, _ismbstrail_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|Sondaki bayt (bağlamında dize)|
|[_mbbtype, _mbbtype_l](../c-runtime-library/reference/mbbtype-mbbtype-l.md)|Önceki bayt üzerinde göre dönüş bayt türü|
|[_mbsbtype, _mbsbtype_l](../c-runtime-library/reference/mbsbtype-mbsbtype-l.md)|Dönüş türü dize içindeki bayt|
|[mbsinit](../c-runtime-library/reference/mbsinit.md)|Çok baytlı bir karakter dönüştürme durumunu izler.|

**MB_LEN_MAX** tanımlı makro \<lımıts.h >, herhangi bir karakterin olabilir bayt cinsinden en büyük uzunluğu genişletir. **MB_CUR_MAX**içinde tanımlanmış \<stdlib.h >, herhangi bir karakterin geçerli ayardaki bayt cinsinden en büyük uzunluğu genişletir.

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)