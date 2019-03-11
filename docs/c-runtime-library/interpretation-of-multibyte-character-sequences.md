---
title: Çok Baytlı Karakter Sıralarının Yorumu
ms.date: 04/11/2018
f1_keywords:
- c.character.multibyte
helpviewer_keywords:
- MBCS [C++], locale code page
ms.assetid: da9150de-70ea-4d2f-90e6-ddb9202dd80b
ms.openlocfilehash: 68a0fdf0bdb573b40d347e05a7449affda55d8e5
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738835"
---
# <a name="interpretation-of-multibyte-character-sequences"></a>Çok Baytlı Karakter Sıralarının Yorumu

Microsoft Çalışma Zamanı Kitaplığı'ndaki en çok baytlı karakter yordamlarını, çok baytlı karakter dizileri ile ilgili bir çok baytlı kod sayfasına tanır. Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** soneki geçerli yerel ayarı kullanır bu yerel ayara bağlı davranışı için; sürümleriyle **_l** sonekine bunların yerel ayar parametresini kullanmalarıdır Bunun yerine iletilmiş.

## <a name="locale-dependent-multibyte-routines"></a>Çok baytlı yerel ayara bağımlı yordamlar

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_mbclen, mblen, _mblen_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Doğrulama ve çok baytlı karakterdeki bayt sayısını döndürür|
|[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|Çok baytlı karakter dizelerini:; dizesindeki her karakterle doğrula dize uzunluğunu döndürür. Geniş karakter dizeleri: dize uzunluğunu döndürür.|
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Dizi çok baytlı karakteri karşılık gelen geniş karakterler dizisi için Dönüştür|
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Karşılık gelen geniş karakter için çok baytlı karakter dönüştürme|
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Geniş karakter dizisi karşılık gelen çok baytlı karakter dizisine dönüştürme|
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Çok baytlı karaktere karşılık gelen geniş karakter dönüştürme|
|[mbrtoc16, mbrtoc32](../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)|Çok baytlı karakter eşdeğer UTF-16 veya UTF-32 karakter dönüştürme|
|[c16rtomb, c32rtomb](../c-runtime-library/reference/c16rtomb-c32rtomb1.md)|UTF-16 veya UTF-32 karakter eşdeğer çok baytlı karakter dönüştürme|

## <a name="see-also"></a>Ayrıca bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
