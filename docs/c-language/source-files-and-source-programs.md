---
title: Kaynak Dosyalar ve Kaynak Programlar
ms.date: 11/04/2016
helpviewer_keywords:
- files [C++], source
- programs [C++], source
- source files, specifying in compiler
- source programs
ms.assetid: 18bb2826-17da-48e5-92a2-10e649f1bc9f
ms.openlocfilehash: c9a7c17c5cf52cb263d61fe79baa331c5b4d57a5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637159"
---
# <a name="source-files-and-source-programs"></a>Kaynak Dosyalar ve Kaynak Programlar

Kaynak programı bir veya daha fazla "kaynak dosyaya" veya "çeviri birimine" ayrılabilir. Derleyici girişine "çeviri birimi" denir.

## <a name="syntax"></a>Sözdizimi

*Çeviri birimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Dış bildirimi* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Çeviri birimi* *dış bildirimi*

*Dış bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işlev tanımı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi*

[Bildirimlere genel bakış](../c-language/overview-of-declarations.md) için sözdizimini sağlar `declaration` bildirimlere ve *önişlemci başvurusu* açıklar nasıl [çeviri birimi](../preprocessor/phases-of-translation.md) işlenir.

> [!NOTE]
>  Giriş bkz [C dili sözdizimi özeti](../c-language/c-language-syntax-summary.md), ANSI sözdizimi kurallarının açıklaması için.

Çeviri biriminin bileşenleri, işlev tanımları ve tanımlayıcı bildirimleri içeren dış bildirimlerdir. Bu bildirimler ve tanımlar, kaynak dosyalarında, üstbilgi dosyalarında, kitaplıklarda ve programın ihtiyacı olan diğer dosyalarda olabilir. Bir program oluşturmak için her çeviri birimini derlemeniz ve ortaya çıkan nesne dosyalarını bağlamanız gerekir.

C "kaynak programı" yönergeler, pragmalar, bildirimler, tanımlar, deyim blokları ve işlevlerden oluşan bir koleksiyondur. Microsoft C programının geçerli bileşenleri olabilmeleri için her birinin, programda herhangi bir sırada görünebilmelerine rağmen (bu kılavuz boyunca açıklanan kurallara tabi olarak) bu kılavuzda açıklanan sözdizimine sahip olması gerekir. Ancak, bu bileşenlerin programdaki konumu, değişkenlerin ve işlevlerin programda nasıl kullanılabileceğini etkiler. (Bkz [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md) daha fazla bilgi için.)

Kaynak dosyalarının yürütülebilir deyimleri içermesine gerek yoktur. Örneğin, değişkenlerin tanımlarını bir kaynak dosyasına yerleştirmeyi ve ardından bu değişkenlere yapılan başvuruları bunları kullanan başka kaynak dosyalarında bildirmeyi yararlı bulabilirsiniz. Bu teknik, gerektiğinde tanımların bulunmasını ve güncelleştirilmesini kolaylaştırır. Aynı nedenle sabitler ve makrolar, çoğu zaman gerektiğinde kaynak dosyalarında başvurulabilen "içerme dosyaları" veya "üstbilgi dosyaları" adlı ayrı dosyalar halinde düzenlenebilir. Bkz: *önişlemci başvurusu* hakkında bilgi için [makroları](../preprocessor/macros-c-cpp.md) ve [içerme dosyaları](../preprocessor/hash-include-directive-c-cpp.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Program Yapısı](../c-language/program-structure.md)