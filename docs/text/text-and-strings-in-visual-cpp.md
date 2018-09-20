---
title: Visual C++'da metin ve dizeler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 555183de13728cc01509b87e8eca8c3340d2d68b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424069"
---
# <a name="text-and-strings-in-visual-c"></a>Visual C++'da Metin ve Dizeler

Uluslararası pazarlar için uygulama geliştirmenin önemli bir yönüdür yerel karakter kümeleri yeterli gösterimidir. ASCII karakter kümesi aralığı için 0x00 0x7F karakter tanımlar. Karakterler için 0x00 0x7F aralık içinde aynı şekilde ASCII karakter kümesi tanımlayan ve ayrıca genişletilmiş bir karakter 0x80 için 0xFF kümesini tanımlamak öncelikle Avrupa, diğer karakter kümesi vardır. Bu nedenle, 8-bit, tek baytlı karakter kümesi (SBCS) birçok Avrupa dilleri için karakter kümesi yanı sıra ASCII karakter kümesi temsil etmek yeterli olur. Ancak, bazı Avrupa dışı karakter kümeleri, Japonca Kanji gibi tek bayt kodlama düzenini temsil eden ve çok baytlı karakter kodlaması (MBCS) ayarlayın. Bu nedenle gerekli olandan çok daha fazla karakter içerir.

## <a name="in-this-section"></a>Bu Bölümde

[Unicode ve MBCS](../text/unicode-and-mbcs.md)<br/>
Unicode ve MBCS programlama için Visual C++ desteği açıklanmaktadır.

[Unicode Desteği](../text/support-for-unicode.md)<br/>
Unicode olarak temsil edilemeyen bir karakter kümesi tek bir bayt dahil olmak üzere, tüm karakter kümeleri destekleyen bir belirtim açıklar.

[Çok baytlı karakter kümesi (MBCS) için destek](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
MBCS, Unicode karakter kümesi, Japonca ve Çince tek bir bayt ile gösterilemez gibi destekleyici alternatif açıklanır.

[Tchar.h'de Genel Metin Eşlemeleri](../text/generic-text-mappings-in-tchar-h.md)<br/>
Microsoft'a özgü genel metin eşlemeleri birçok veri türleri, yordamlar ve diğer nesneleri sağlar.

[Nasıl yapılır: Çeşitli Dize Türleri Arasında Dönüştürme Yapma](../text/how-to-convert-between-various-string-types.md)<br/>
Çeşitli Visual C++ dize türlerinin diğer dizelere dönüştürülebileceği gösterilmektedir.

## <a name="related-sections"></a>İlgili Bölümler

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
Uluslararası Destek C Çalışma Zamanı Kitaplığı'nda açıklanır.

[Uluslararası örnekler](https://github.com/Microsoft/VCSamples)<br/>
Visual c++ uluslararası gösteren örneklere bağlantılar sağlar.

[Dil ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
C çalışma zamanı kitaplığı dil ve ülke/bölge dizeleri sağlar.