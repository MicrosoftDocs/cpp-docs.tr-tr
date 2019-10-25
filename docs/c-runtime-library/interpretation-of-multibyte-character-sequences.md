---
title: Çok baytlı karakter sıralarının yorumu
ms.date: 10/22/2019
f1_keywords:
- c.character.multibyte
helpviewer_keywords:
- MBCS [C++], locale code page
ms.assetid: da9150de-70ea-4d2f-90e6-ddb9202dd80b
ms.openlocfilehash: 7431f0c63df60414af192ea38103318c775c430d
ms.sourcegitcommit: 0a5518fdb9d87fcc326a8507ac755936285fcb94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72811083"
---
# <a name="interpretation-of-multibyte-character-sequences"></a>Çok baytlı karakter sıralarının yorumu

Microsoft çalışma zamanı kitaplığındaki çok baytlı karakter düzenleri, çok baytlı kod sayfasıyla ilgili çok baytlı karakter dizilerini tanır. Çıkış değeri, yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir. Daha fazla bilgi için bkz. [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). **_L** sonekine sahip olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_L** sonekine sahip sürümler, geçerli yerel ayar yerine yerel ayar parametresini kullanmaları dışında aynıdır.

## <a name="locale-dependent-multibyte-routines"></a>Yerel ayara bağımlı çok baytlı yordamlar

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_mbclen, mblen, _mblen_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Çok baytlı karakterdeki bayt sayısını doğrulayın ve döndürün|
|[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|Çok baytlı karakter dizeleri için: dizedeki her karakteri doğrulama; dönüş dizesi uzunluğu. Geniş karakter dizeleri için: dize uzunluğunu döndürür.|
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Çok baytlı karakterlerin dizisini karşılık gelen geniş karakter dizisine Dönüştür|
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Çok baytlı karakteri karşılık gelen geniş karaktere Dönüştür|
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Geniş karakter sırasını, çok baytlı karakterlerin karşılık gelen dizisine Dönüştür|
|[wctomb, _wckaldırıldı _l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb_s, _wckaldırıldı _s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Geniş karakteri karşılık gelen çok baytlı karaktere Dönüştür|

## <a name="locale-independent-multibyte-routines"></a>Yerel ayar bağımsız çok baytlı yordamları

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[mbrtoc16, mbrtoc32](../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)|Çok baytlı UTF-8 karakterini eşit UTF-16 veya UTF-32 karakterine Dönüştür|
|[c16rtomb, c32rtomb](../c-runtime-library/reference/c16rtomb-c32rtomb1.md)|UTF-16 veya UTF-32 karakterini eşit UTF-8 çok baytlı karaktere Dönüştür|

## <a name="see-also"></a>Ayrıca bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)\
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)
