---
title: Uluslararası Etkinleştirme
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- strings [C++], international enabling
- localization [C++], character sets
- MBCS [C++], enabling
- Unicode [C++], enabling
ms.assetid: b077f4ca-5865-40ef-a46e-d9e4d686ef21
ms.openlocfilehash: b6c645bafef87ed0b2d43903f4752ef659d79f89
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375802"
---
# <a name="international-enabling"></a>Uluslararası Etkinleştirme

Geleneksel C ve C++ kodunun çoğu, uluslararası uygulamalar için iyi çalışmayan karakter ve dize işleme hakkında varsayımlar yapar. Hem MFC hem de çalışma zamanı kitaplığı Unicode veya MBCS'yi desteklerken, yapmanız gereken işler devam eder. Bu bölümde size rehberlik etmek için Visual C++'da "uluslararası etkinleştirme"nin anlamı açıklanmaktadır:

- Hem Unicode hem de MBCS, MFC işlev parametre listelerindeki taşınabilir veri türleri ve iade türleri ile etkinleştirilir. Bu türler, yapınızın sembolü `_UNICODE` veya sembolü `_MBCS` (DBCS anlamına gelir) tanımlayıp tanımlamadığına bağlı olarak uygun şekilde koşullu olarak tanımlanır. MFC kitaplıklarının farklı türevleri, yapınızın tanımladığı bu iki simgeden hangisine bağlı olarak uygulamanızla otomatik olarak bağlanır.

- Sınıf kitaplığı kodu, unicode veya MBCS davranışını düzeltmek için taşınabilir çalışma zamanı işlevlerini ve diğer araçları kullanır.

- Yine de kodunuzda belirli türde uluslararasılaştırma görevlerini yerine getirmeniz gerekir:

  - MFC'yi her iki ortamda da taşınabilir yapan aynı taşınabilir çalışma zamanı işlevlerini kullanın.

  - Makroyu kullanarak, gerçek dizeleri ve karakterleri `_T` her iki ortam altında taşınabilir hale getirin. Daha fazla bilgi için [tchar.h'deki Genel Metin Eşlemeleri'ne](../text/generic-text-mappings-in-tchar-h.md)bakın.

  - MBCS altında dizeleri ayrıştırken önlem alın. Bu önlemler Unicode altında gerekli değildir. Daha fazla bilgi için [MBCS Programlama İpuçları'na](../text/mbcs-programming-tips.md)bakın.

  - Uygulamanızda ANSI (8-bit) ve Unicode (16 bit) karakterleri karıştırırsanız dikkatli olun. Programın bazı bölümlerinde ANSI, diğerlerinde Unicode karakterleri kullanmak mümkündür, ancak bunları aynı dizede karıştıramazsınız.

  - Uygulamanızda dizeleri sabit kodlamayın. Bunun yerine, uygulamanın .rc dosyasına ekleyerek stringtable kaynaklarını yapın. Uygulamanız daha sonra kaynak kodu değişiklikleri veya yeniden derleme gerektirmeden yerelleştirilmiş olabilir. STRINGTABLE kaynakları hakkında daha fazla bilgi için [String Editor'a](../windows/string-editor.md)bakın.

> [!NOTE]
> Avrupa ve MBCS karakter kümelerinde, karakter kodları 0x80'den büyük olan aksanlı harfler gibi bazı karakterler bulunur. Çoğu kod imzalı karakterler kullandığından, 0x80'den büyük bu karakterler **int'e**dönüştürüldüğünde imzaya uzatılır. Bu dizi dizi dizileme için bir sorundur, çünkü işaret genişletilmiş karakterler, negatif olmak, dizi dışında dizinler. Japonca gibi MBCS kullanan diller de benzersizdir. Bir karakter 1 veya 2 bayttan oluşabileceğinden, her iki baytı da aynı anda manipüle etmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Unicode ve MBCS](../text/unicode-and-mbcs.md)<br/>
[Uluslararası Duruma Getirme Stratejileri](../text/internationalization-strategies.md)
