---
description: 'Daha fazla bilgi edinin: Visual C++ metin ve dizeler'
title: Visual C++'da Metin ve Dizeler
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- programming [C++], international
- multiple language support [C++]
- Unicode [C++]
- international applications [C++], about international applications
- portability [C++]
- translation [C++], character sets
- non-European characters [C++]
- character sets [C++]
- globalization [C++]
- Japanese characters [C++]
- Kanji character support [C++]
- local character sets [C++]
- ASCII characters [C++]
- character sets [C++], about character sets
- localization [C++], character sets
- translating code [C++]
- localization [C++]
- character sets [C++], non-European
- portability [C++], character sets
- MBCS [C++], international programming
ms.assetid: a1bb27ac-abe5-4c6b-867d-f761d4b93205
ms.openlocfilehash: 3b77df006e095871d11fb3bfbc3d83b081d6052f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335729"
---
# <a name="text-and-strings-in-visual-c"></a>Visual C++'da Metin ve Dizeler

Uluslararası pazarlar için uygulama geliştirmenin önemli bir yönü, yerel karakter kümelerinin yeterli gösterimidir. ASCII karakter kümesi, 0x00 ile 0x7F aralığındaki karakterleri tanımlar. 0x00-0x7F aralığındaki karakterleri ASCII karakter kümesiyle aynı şekilde tanımlayan ve ayrıca 0x80 ' dan 0xFF 'e genişletilmiş bir karakter kümesi tanımlayan, birincil olarak Avrupa 'daki diğer karakter kümeleri vardır. Bu nedenle, bir 8 bit, tek baytlık karakter kümesi (SBCS) ASCII karakter kümesini temsil etmek için yeterlidir ve birçok Avrupa dili için karakter kümelerini de belirler. Ancak, Japonca Kanji gibi bazı Avrupa olmayan karakter kümeleri, tek baytlık bir kodlama düzeninden çok daha fazla karakter içerir ve bu nedenle çok baytlı karakter kümesi (MBCS) kodlaması gerektirir.

## <a name="in-this-section"></a>Bu Bölümde

[Unicode ve MBCS](../text/unicode-and-mbcs.md)<br/>
Unicode ve MBCS programlamasına yönelik Visual C++ desteğini açıklar.

[Unicode desteği](../text/support-for-unicode.md)<br/>
Tek bir bayt içinde temsil edilemeyecek karakter kümeleri de dahil olmak üzere tüm karakter kümelerini desteklemeye yönelik bir belirtim olan Unicode ' u açıklar.

[Çok baytlı karakter kümesi desteği (MBCS)](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
Japonca ve Çince gibi tek bir baytta temsil edilemeyecek karakter kümelerini desteklemek için Unicode 'a alternatif olarak MBCS 'yi açıklar.

[Tchar. h 'de Genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md)<br/>
Birçok veri türü, yordamlar ve diğer nesneler için Microsoft 'a özgü genel metin eşlemeleri sağlar.

[Nasıl yapılır: çeşitli dize türleri arasında dönüştürme](../text/how-to-convert-between-various-string-types.md)<br/>
Çeşitli Visual C++ dize türlerinin diğer dizelere nasıl dönüştürüleceğini gösterir.

## <a name="related-sections"></a>İlgili Bölümler

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
C çalışma zamanı kitaplığı 'nda uluslararası desteği açıklar.

[Uluslararası örnekler](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/International)<br/>
Visual C++ uluslararası duruma getirme gösteren örneklere bağlantılar sağlar.

[Dil ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
C çalışma zamanı kitaplığındaki dili ve ülke/bölge dizelerini sağlar.
