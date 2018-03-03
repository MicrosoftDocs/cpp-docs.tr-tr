---
title: "Çok baytlı karakter sıralarının yorumu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.character.multibyte
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], locale code page
ms.assetid: da9150de-70ea-4d2f-90e6-ddb9202dd80b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 90f7f9431ddfc2d21a29b35643ee3dff3e34cd6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="interpretation-of-multibyte-character-sequences"></a>Çok Baytlı Karakter Sıralarının Yorumu
Microsoft Çalışma Zamanı Kitaplığı'ndaki en çok baytlı karakter yordamları için birden çok baytlı kod sayfası ile ilgili çok baytlı karakter sıralarının farkındayız. Çıkış değerini ayarı tarafından etkilenen `LC_CTYPE` yerel kategori ayarı; bkz: [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri `_l` bu yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; sürümleriyle `_l` soneki, bunun yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.  
  
### <a name="locale-dependent-multibyte-routines"></a>Yerel ayara bağımlı birden çok baytlı yordamları  
  
|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|-------------|---------|  
|[_mbclen, mblen, _mblen_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Birden çok baytlı karakter bayt sayısını döndürmek ve doğrulama|  
|[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|Birden çok baytlı karakter dizeleri: dize; her karakter doğrula dize uzunluğu döndür. Geniş karakter dizelerini: dize uzunluğunu döndür.|  
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Geniş karakterler karşılık gelen bir dizi için birden çok baytlı karakter dizisi Dönüştür|  
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Birden çok baytlı karakter karşılık gelen geniş karakter dönüştürme|  
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Birden çok baytlı karakterler karşılık gelen bir dizi için geniş bir karakter dizisi Dönüştür|  
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Geniş karakter karşılık gelen birden çok baytlı karakter dönüştürme|  
|[mbrtoc16, mbrtoc32](../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)|Birden çok baytlı karakter eşdeğer UTF-16 veya UTF-32 karakter dönüştürme|  
|[c16rtomb, c32rtomb](../c-runtime-library/reference/c16rtomb-c32rtomb1.md)|UTF-16 veya UTF-32 karakter eşdeğer birden çok baytlı karakter dönüştürme|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uluslararası duruma getirme](../c-runtime-library/internationalization.md)   
 [Kategorilere Göre Çalışma Zamanı Yordamları](../c-runtime-library/run-time-routines-by-category.md)