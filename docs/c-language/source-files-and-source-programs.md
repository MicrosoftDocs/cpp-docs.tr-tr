---
title: Kaynak Dosyalar ve Kaynak Programlar
ms.date: 11/04/2016
helpviewer_keywords:
- files [C++], source
- programs [C++], source
- source files, specifying in compiler
- source programs
ms.assetid: 18bb2826-17da-48e5-92a2-10e649f1bc9f
ms.openlocfilehash: ac906925be551c6ee4da08e200d4028047b3d041
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349888"
---
# <a name="source-files-and-source-programs"></a>Kaynak Dosyalar ve Kaynak Programlar

Kaynak programı bir veya daha fazla "kaynak dosyaya" veya "çeviri birimine" ayrılabilir. Derleyici girişine "çeviri birimi" denir.

## <a name="syntax"></a>Sözdizimi

*çeviri birimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*dış beyan* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*çeviri birimi* *dış beyan*

*dış beyan*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*fonksiyon tanımı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirim*

[Bildirimlere Genel Bakış,](../c-language/overview-of-declarations.md) nonterminal `declaration` için sözdizimini verir ve *Önİşlemci Başvurusu* [çeviri biriminin](../preprocessor/phases-of-translation.md) nasıl işlenirolduğunu açıklar.

> [!NOTE]
> ANSI sözdizimi sözleşmelerinin açıklaması için [C Dili Sözdizimi Özeti'ne](../c-language/c-language-syntax-summary.md)giriş bölümüne bakın.

Çeviri biriminin bileşenleri, işlev tanımları ve tanımlayıcı bildirimleri içeren dış bildirimlerdir. Bu bildirimler ve tanımlar, kaynak dosyalarında, üstbilgi dosyalarında, kitaplıklarda ve programın ihtiyacı olan diğer dosyalarda olabilir. Bir program oluşturmak için her çeviri birimini derlemeniz ve ortaya çıkan nesne dosyalarını bağlamanız gerekir.

C "kaynak programı" yönergeler, pragmalar, bildirimler, tanımlar, deyim blokları ve işlevlerden oluşan bir koleksiyondur. Microsoft C programının geçerli bileşenleri olabilmeleri için her birinin, programda herhangi bir sırada görünebilmelerine rağmen (bu kılavuz boyunca açıklanan kurallara tabi olarak) bu kılavuzda açıklanan sözdizimine sahip olması gerekir. Ancak, bu bileşenlerin programdaki konumu, değişkenlerin ve işlevlerin programda nasıl kullanılabileceğini etkiler. (Daha fazla bilgi için [Bkz. Yaşam Süresi, Kapsam, Görünürlük ve Bağlantı.)](../c-language/lifetime-scope-visibility-and-linkage.md)

Kaynak dosyalarının yürütülebilir deyimleri içermesine gerek yoktur. Örneğin, değişkenlerin tanımlarını bir kaynak dosyasına yerleştirmeyi ve ardından bu değişkenlere yapılan başvuruları bunları kullanan başka kaynak dosyalarında bildirmeyi yararlı bulabilirsiniz. Bu teknik, gerektiğinde tanımların bulunmasını ve güncelleştirilmesini kolaylaştırır. Aynı nedenle sabitler ve makrolar, çoğu zaman gerektiğinde kaynak dosyalarında başvurulabilen "içerme dosyaları" veya "üstbilgi dosyaları" adlı ayrı dosyalar halinde düzenlenebilir. [Makrolar](../preprocessor/macros-c-cpp.md) hakkında bilgi ve dosyaları [eklemek](../preprocessor/hash-include-directive-c-cpp.md)için *Önİşlemci Başvurusu'na* bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Program Yapısı](../c-language/program-structure.md)
