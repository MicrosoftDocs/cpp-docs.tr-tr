---
description: 'Daha fazla bilgi edinin: kaynak dosyalar ve kaynak programlar'
title: Kaynak Dosyalar ve Kaynak Programlar
ms.date: 11/04/2016
helpviewer_keywords:
- files [C++], source
- programs [C++], source
- source files, specifying in compiler
- source programs
ms.assetid: 18bb2826-17da-48e5-92a2-10e649f1bc9f
ms.openlocfilehash: 9fd389f74efac11288b805d95dc2d95d4ec6d2bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296907"
---
# <a name="source-files-and-source-programs"></a>Kaynak Dosyalar ve Kaynak Programlar

Kaynak programı bir veya daha fazla "kaynak dosyaya" veya "çeviri birimine" ayrılabilir. Derleyici girişine "çeviri birimi" denir.

## <a name="syntax"></a>Syntax

*çeviri birimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Dış bildirim* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*çeviri birimi* *dış bildirimi*

*Dış bildirim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işlev tanımı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bağımsız*

[Bildirimlere genel bakış](../c-language/overview-of-declarations.md) , terminal dışı için söz dizimini verir `declaration` ve *Önişlemci Başvurusu* , [çeviri biriminin](../preprocessor/phases-of-translation.md) nasıl işlendiğini açıklar.

> [!NOTE]
> ANSI sözdizimi kurallarının açıklaması için [C dili sözdizimi özetine](../c-language/c-language-syntax-summary.md)giriş bölümüne bakın.

Çeviri biriminin bileşenleri, işlev tanımları ve tanımlayıcı bildirimleri içeren dış bildirimlerdir. Bu bildirimler ve tanımlar, kaynak dosyalarında, üstbilgi dosyalarında, kitaplıklarda ve programın ihtiyacı olan diğer dosyalarda olabilir. Bir program oluşturmak için her çeviri birimini derlemeniz ve ortaya çıkan nesne dosyalarını bağlamanız gerekir.

C "kaynak programı" yönergeler, pragmalar, bildirimler, tanımlar, deyim blokları ve işlevlerden oluşan bir koleksiyondur. Microsoft C programının geçerli bileşenleri olabilmeleri için her birinin, programda herhangi bir sırada görünebilmelerine rağmen (bu kılavuz boyunca açıklanan kurallara tabi olarak) bu kılavuzda açıklanan sözdizimine sahip olması gerekir. Ancak, bu bileşenlerin programdaki konumu, değişkenlerin ve işlevlerin programda nasıl kullanılabileceğini etkiler. (Daha fazla bilgi için bkz. [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md) .)

Kaynak dosyalarının yürütülebilir deyimleri içermesine gerek yoktur. Örneğin, değişkenlerin tanımlarını bir kaynak dosyasına yerleştirmeyi ve ardından bu değişkenlere yapılan başvuruları bunları kullanan başka kaynak dosyalarında bildirmeyi yararlı bulabilirsiniz. Bu teknik, gerektiğinde tanımların bulunmasını ve güncelleştirilmesini kolaylaştırır. Aynı nedenle sabitler ve makrolar, çoğu zaman gerektiğinde kaynak dosyalarında başvurulabilen "içerme dosyaları" veya "üstbilgi dosyaları" adlı ayrı dosyalar halinde düzenlenebilir. [Makrolar](../preprocessor/macros-c-cpp.md) ve [içerme dosyaları](../preprocessor/hash-include-directive-c-cpp.md)hakkında bilgi Için bkz. *Önişlemci Başvurusu* .

## <a name="see-also"></a>Ayrıca bkz.

[Program yapısı](../c-language/program-structure.md)
