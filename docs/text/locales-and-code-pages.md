---
title: Yerel Ayarlar ve Kod Sayfaları
ms.date: 11/04/2016
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
ms.openlocfilehash: 0015e0a7a81abbd3472a8c845a9b8c0d8caf4618
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610546"
---
# <a name="locales-and-code-pages"></a>Yerel Ayarlar ve Kod Sayfaları

Bir yerel ayar kimliği, belirli bir coğrafi bölge için dili ve yerel kurallarını yansıtır. Belirli bir dile birden fazla ülkede/bölgede konuşulan; Örneğin, Brezilya'da de Portekiz olduğu gibi Portekizce konuşulan. Buna karşılık, bir ülke/bölge, birden fazla dil olabilir. Örneğin, iki dilden Kanada vardır: İngilizce ve Fransızca. Bu nedenle, Kanada, iki farklı yerel ayarlar vardır: Kanada İngilizce ve Fransızca Kanada. Bazı yerel ayara bağımlı kategoriler tarih biçimlendirmesini ve parasal değerlerin görüntülenme biçimini içerir.

Metin ve biçimlendirme kurallarını ülke/bölge yerel kuralları belirlerken veri dili belirler. Her dil alfabe (örneğin, noktalama işaretleri ve sayılar) dışındaki karakterler içeren kod sayfaları tarafından temsil edilen bir benzersiz eşlemesi vardır. Bir kod sayfasında karakter kümesi ve dille ilgili. Bu nedenle, bir [yerel ayar](../c-runtime-library/locale.md) benzersiz bir dil, ülke/bölge ve kod sayfası birleşimidir. Yerel ayar ve kod sayfası ayarı çağırarak çalışma zamanında değiştirilebilir [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) işlevi.

Farklı dillerde farklı kod sayfalarını kullanabilir. Örneğin, ANSI kod sayfası 1252 İngilizce ve birçok Avrupa dilleri için kullanılır ve ANSI kod sayfası 932'de Japonca Kanji için kullanılır. Neredeyse tüm kod sayfaları ASCII karakter düşük 128 karakter (0x00-0x7F) kümesini paylaşır.

Herhangi bir tek baytlı kod sayfası (256 girişleri ile) bir tablodaki bayt değerleri (sayılar ve noktalama işaretleri dahil) karakteri veya karakterleri eşlemesi olarak gösterilebilir. Herhangi bir çok baytlı kod sayfasında karakter çift bayt değerleri (girişlerle 64 K) çok büyük bir tablo olarak da temsil edilebilir. Uygulamada, ancak bu genellikle gösterilir (tek bayt) ilk 256 karakteri için bir tabloyu ve çift bayt değerleri için aralığı olarak.

Kod sayfaları hakkında daha fazla bilgi için bkz. [kod sayfaları](../c-runtime-library/code-pages.md).

C çalışma zamanı kitaplığı iç kod sayfaları iki tür vardır: yerel ayar ve çok baytlı. Program yürütülmesi sırasında mevcut kod sayfasında değiştirebilirsiniz (belgelerine bakın [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) ve [_setmbcp](../c-runtime-library/reference/setmbcp.md) işlevler). Ayrıca, çalışma zamanı kitaplığı bir almak ve program yürütme süresi boyunca sabit olan işletim sistemi kod sayfasını kullanın.

Yerel ayar kod sayfası değiştiğinde seçilen kod sayfası tarafından dikte işlevleri değişiklikleri yerel ayara bağımlı kümesini davranışı. Varsayılan olarak, tüm yerel ayara bağlı İşlevler, yürütme "C" yerel ayarı için benzersiz bir yerel ayar kod sayfası ile başlayın. İç yerel ayar kod sayfası (yanı sıra diğer yerel ayara özgü özellikleri) çağırarak değiştirebilirsiniz `setlocale` işlevi. Bir çağrı `setlocale`(LC_ALL, "") yerel ayarı işletim sistemi kullanıcı yerel ayar tarafından belirtilen ayarlar.

Benzer şekilde, çok baytlı kod sayfasına değiştiğinde, seçilen kod sayfası tarafından dikte çok baytlı işlevleri değişiklikleri davranışı. Varsayılan olarak, tüm çok baytlı işlevler işletim sisteminin varsayılan kod sayfasına karşılık gelen bir çok baytlı kod sayfası ile yürütme başlar. İç çok baytlı kod sayfası çağırarak değiştirebilirsiniz `_setmbcp` işlevi.

C çalışma zamanı işlevi `setlocale` ayarlar, değiştirir veya bazılarını veya tümünü geçerli programın yerel ayar bilgilerinin sorgular. [_Wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) yordamdır, bir geniş karakter sürümünü `setlocale`; bağımsız değişkenler ve dönüş değerleri `_wsetlocale` geniş karakterli dizelerdir.

## <a name="see-also"></a>Ayrıca Bkz.

[Unicode ve MBCS](../text/unicode-and-mbcs.md)<br/>
[Karakter Kümesi Taşınabilirliğinin Yararları](../text/benefits-of-character-set-portability.md)