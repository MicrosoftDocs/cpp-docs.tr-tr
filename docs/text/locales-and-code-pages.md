---
title: Yerel ayarlar ve kod sayfaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- locales [C++], about locales
- locale IDs [C++]
- locales [C++]
- code pages [C++]
- code pages [C++], dynamically changing
- character sets [C++], code pages
- multibyte code pages [C++]
- character sets [C++], locales
- localization [C++], code pages
- localization [C++], locales
- code pages [C++], locales
- conventions [C++], international character support
ms.assetid: bd937361-b6d3-4c98-af95-beb7c903187b
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1c7dd3c5356df7b80f21605e325158e87cc5a71
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858152"
---
# <a name="locales-and-code-pages"></a>Yerel Ayarlar ve Kod Sayfaları
Yerel ayar kimliği, belirli bir coğrafi bölge için dili ve yerel kuralları yansıtır. Belirli bir dile birden fazla ülke/bölge içinde konuşulan; Örneğin, Portekizce de olduğu gibi Portekiz Brezilya konuşulmaz. Buna karşılık, bir ülke veya bölgeye birden fazla resmi dili olabilir. Örneğin, iki dil Kanada vardır: İngilizce ve Fransızca. Bu nedenle, Kanada iki ayrı yerel ayarı vardır: Kanada İngilizce ve Fransızca Kanada. Bazı yerel ayara bağımlı kategoriler tarih biçimlendirmesini ve parasal değerlerin görüntülenme biçimini içerir.  
  
 Metin ve biçimlendirme kurallarını ülke/bölge yerel kuralları belirlerken veri dilini belirler. Her dilin olanlar (örneğin, noktalama işaretleri ve sayılar) alfabedeki dışında karakterler içeren kod sayfaları tarafından temsil edilen bir benzersiz eşlemesi vardır. Kod sayfası, bir karakter kümesidir ve dille ilgili. Bu nedenle, bir [yerel](../c-runtime-library/locale.md) benzersiz bir dil, ülke/bölge ve kod sayfası birleşimidir. Yerel ayar ve kod sayfası ayarı çağırarak çalışma zamanında değiştirilebilir [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) işlevi.  
  
 Farklı diller farklı kod sayfaları kullanabilir. Örneğin, ANSI kod sayfası 1252 İngilizce ve birçok Avrupa dilleri için kullanılır ve ANSI kod sayfası 932 Japonca Kanji için kullanılır. Neredeyse tüm kod sayfaları ASCII karakter düşük 128 karakterden (0x00-0x7F) kümesini paylaşır.  
  
 Tüm tek baytlı kod sayfası (olan 256 girişleri) bir tabloda (sayıları ve noktalama işaretlerini dahil) karakter ya da karakterlerin bayt değerleri eşlemesi olarak gösterilebilir. Çok baytlı kod sayfası (64 K girişlerle) çok büyük bir tablo çift baytlık karakterler değerlerin olarak da temsil edilebilir. Uygulamada, ancak bunu genellikle temsil ilk 256 (tek baytlı) karakterler için tablo ve çift baytlı değerlerin aralıkları olarak.  
  
 Kod sayfaları hakkında daha fazla bilgi için bkz: [kod sayfaları](../c-runtime-library/code-pages.md).  
  
 C çalışma zamanı kitaplığı iç kod sayfaları iki tür vardır: yerel ayar ve çok baytlı. Program yürütülmesi sırasında geçerli kod sayfası değiştirebilirsiniz (belgelerine bakın [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) ve [_setmbcp](../c-runtime-library/reference/setmbcp.md) işlevleri). Ayrıca, çalışma zamanı kitaplığı bir elde edilir ve program yürütme süresi için sabittir işletim sistemi kod sayfası değerini kullanın.  
  
 Yerel ayar kod sayfası değiştiğinde seçilen kod sayfası tarafından dikte işlevleri değişiklikler yerel ayara bağımlı kümesi davranışını. Varsayılan olarak, tüm yerel ayara bağımlı işlevleri yürütme "C" yerel ayar için benzersiz bir yerel ayar kod sayfası ile başlar. İç yerel ayar kod sayfası (yanı sıra diğer yerel ayarlara özgü özellikleri) çağırarak değiştirebileceğiniz `setlocale` işlevi. Çağrı `setlocale`(LC_ALL, "") yerel işletim sisteminin kullanıcı yerel ayarı tarafından belirtilen ayarlar.  
  
 Benzer şekilde, birden çok baytlı kod sayfası değiştiğinde, birden çok baytlı işlevleri yapılan değişiklikler seçilen kod sayfası tarafından dikte davranışını. Varsayılan olarak, tüm birden çok baytlı işlevleri yürütme işletim sisteminin varsayılan kod sayfasına karşılık gelen bir birden çok baytlı kod sayfası ile başlar. İç birden çok baytlı kod sayfası çağırarak değiştirebileceğiniz `_setmbcp` işlevi.  
  
 C çalışma zamanı işlevi `setlocale` ayarlar, değiştirir veya bazılarını veya tümünü geçerli programın yerel ayar bilgileri sorgular. [_Wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) yordamdır bir joker karakter sürümü `setlocale`; değişkenler ve dönüş değerleri `_wsetlocale` joker karakter dizelerdir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Unicode ve MBCS](../text/unicode-and-mbcs.md)   
 [Karakter Kümesi Taşınabilirliğinin Yararları](../text/benefits-of-character-set-portability.md)