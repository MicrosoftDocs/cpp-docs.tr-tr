---
description: 'Daha fazla bilgi edinin: yerel ayarlar ve kod sayfaları'
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
ms.openlocfilehash: f8b5310d7712617b1397bc42ef6ec58e5b3297ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207208"
---
# <a name="locales-and-code-pages"></a>Yerel Ayarlar ve Kod Sayfaları

Yerel ayar KIMLIĞI, belirli bir coğrafi bölgenin yerel kurallarını ve dilini yansıtır. Verilen bir dil birden fazla ülkede/bölgede konuşulmalıdır; Örneğin, Portekizce Portekiz 'de olduğu gibi Brezilya 'da da konuşulur. Buna karşılık, bir ülke/bölge birden fazla resmi dile sahip olabilir. Örneğin, Kanada iki dile sahiptir: Ingilizce ve Fransızca. Bu nedenle Kanada iki farklı yerel ayara sahiptir: Canadian-English ve Kanada Fransızcası. Bazı yerel ayara bağımlı kategoriler tarih biçimlendirmesini ve parasal değerlerin görüntülenme biçimini içerir.

Dil, metin ve veri biçimlendirme kurallarını belirler, ancak ülke/bölge yerel kuralları belirler. Her dilin, alfabede (noktalama işaretleri ve sayılar gibi) farklı karakterler içeren kod sayfalarıyla temsil edilen benzersiz bir eşlemesi vardır. Kod sayfası bir karakter kümesidir ve dille ilgilidir. Bu nedenle, [Yerel](../c-runtime-library/locale.md) bir dil, ülke/bölge ve kod sayfasının benzersiz bir birleşimidir. Yerel ayar ve kod sayfası ayarı, [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) işlevi çağırarak çalışma zamanında değiştirilebilir.

Farklı diller farklı kod sayfaları kullanabilir. Örneğin, ANSI kod sayfası 1252, Ingilizce ve çoğu Avrupa dilinde kullanılır ve ANSI kod sayfası 932, Japonca Kanji için kullanılır. Neredeyse tüm kod sayfaları, ASCII karakter kümesini en düşük 128 karakter (0x00-0x7F ile) için paylaşır.

Herhangi bir tek baytlı kod sayfası, bayt değerlerinin karakterlere (sayılar ve noktalama işaretleri dahil) veya glifleri bir eşleme olarak bir tabloda (256 girişlerle birlikte) temsil edilebilir. Herhangi bir çok baytlı kod sayfası, çift baytlık değerlerin karakterlere göre çok büyük bir tablo (64K girişleri ile) olarak da gösterilebilir. Ancak uygulamada, genellikle ilk 256 (tek baytlık) karakter ve çift baytlık değerler için aralıklar olarak temsil edilir.

Kod sayfaları hakkında daha fazla bilgi için bkz. [kod sayfaları](../c-runtime-library/code-pages.md).

C çalışma zamanı kitaplığı iki tür iç kod sayfasına sahiptir: yerel ayar ve çok baytlı. Program yürütme sırasında geçerli kod sayfasını değiştirebilirsiniz ( [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) ve [_setmbcp](../c-runtime-library/reference/setmbcp.md) işlevleri için belgelere bakın). Ayrıca, çalışma zamanı kitaplığı, programın yürütüldüğü süre için sabit olan işletim sistemi kod sayfasının değerini alabilir ve kullanabilir.

Yerel ayar kodu sayfası değiştiğinde, yerel ayara bağımlı işlevler kümesinin davranışı seçilen kod sayfası tarafından dikte edilen olarak değişir. Varsayılan olarak, yerel ayara bağımlı işlevler, "C" yerel ayarına özgü bir yerel ayar kod sayfasıyla yürütmeye başlar. İşlevi çağırarak iç yerel ayar kod sayfasını (diğer yerel ayara özgü özellikleri) değiştirebilirsiniz `setlocale` . `setlocale`(LC_ALL, "") çağrısı, yerel ayarı işletim sistemi kullanıcı yerel ayarı tarafından belirtilen olarak ayarlar.

Benzer şekilde, çok baytlı kod sayfası değiştiğinde, çok baytlı işlevlerin davranışı seçilen kod sayfası tarafından dikte edilen olarak değişir. Varsayılan olarak, tüm çok baytlı işlevler işletim sisteminin varsayılan kod sayfasına karşılık gelen çok baytlı kod sayfasıyla yürütmeye başlar. İşlevi çağırarak iç çok baytlı kod sayfasını değiştirebilirsiniz `_setmbcp` .

C çalışma zamanı işlevi `setlocale` , geçerli programın yerel ayar bilgilerinin bazılarını veya tümünü ayarlar, değiştirir veya sorgular. [_Wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) yordamı, öğesinin geniş karakterli bir sürümüdür `setlocale` ; bağımsız değişkenler ve dönüş değerleri, `_wsetlocale` geniş karakter dizeleridir.

## <a name="see-also"></a>Ayrıca bkz.

[Unicode ve MBCS](../text/unicode-and-mbcs.md)<br/>
[Karakter kümesi taşınabilirliği 'nin avantajları](../text/benefits-of-character-set-portability.md)
