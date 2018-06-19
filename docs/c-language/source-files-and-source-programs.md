---
title: Kaynak dosyalar ve kaynak programlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- files [C++], source
- programs [C++], source
- source files, specifying in compiler
- source programs
ms.assetid: 18bb2826-17da-48e5-92a2-10e649f1bc9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe7021156f2d24e62590cccbe2feb476a6a642ea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391200"
---
# <a name="source-files-and-source-programs"></a>Kaynak Dosyalar ve Kaynak Programlar
Kaynak programı bir veya daha fazla "kaynak dosyaya" veya "çeviri birimine" ayrılabilir. Derleyici girişine "çeviri birimi" denir.  
  
## <a name="syntax"></a>Sözdizimi  
 *Çeviri birim*:  
 *Dış bildirimi*  
  
 *Çeviri birim dış-bildirimi*  
  
 *Harici bildirim*:  
 *işlev tanımı*  
  
 *bildirimi*  
  
 [Bildirimlere genel bakış](../c-language/overview-of-declarations.md) sözdizimi verir `declaration` nonterminal ve *önişlemci başvurusu* açıklar nasıl [çeviri birim](../preprocessor/phases-of-translation.md) işlenir.  
  
> [!NOTE]
>  Giriş için bkz [C dili sözdizimi özeti](../c-language/c-language-syntax-summary.md), ANSI sözdizimi kurallarına açıklaması için.  
  
 Çeviri biriminin bileşenleri, işlev tanımları ve tanımlayıcı bildirimleri içeren dış bildirimlerdir. Bu bildirimler ve tanımlar, kaynak dosyalarında, üstbilgi dosyalarında, kitaplıklarda ve programın ihtiyacı olan diğer dosyalarda olabilir. Bir program oluşturmak için her çeviri birimini derlemeniz ve ortaya çıkan nesne dosyalarını bağlamanız gerekir.  
  
 C "kaynak programı" yönergeler, pragmalar, bildirimler, tanımlar, deyim blokları ve işlevlerden oluşan bir koleksiyondur. Microsoft C programının geçerli bileşenleri olabilmeleri için her birinin, programda herhangi bir sırada görünebilmelerine rağmen (bu kılavuz boyunca açıklanan kurallara tabi olarak) bu kılavuzda açıklanan sözdizimine sahip olması gerekir. Ancak, bu bileşenlerin programdaki konumu, değişkenlerin ve işlevlerin programda nasıl kullanılabileceğini etkiler. (Bkz [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md) daha fazla bilgi için.)  
  
 Kaynak dosyalarının yürütülebilir deyimleri içermesine gerek yoktur. Örneğin, değişkenlerin tanımlarını bir kaynak dosyasına yerleştirmeyi ve ardından bu değişkenlere yapılan başvuruları bunları kullanan başka kaynak dosyalarında bildirmeyi yararlı bulabilirsiniz. Bu teknik, gerektiğinde tanımların bulunmasını ve güncelleştirilmesini kolaylaştırır. Aynı nedenle sabitler ve makrolar, çoğu zaman gerektiğinde kaynak dosyalarında başvurulabilen "içerme dosyaları" veya "üstbilgi dosyaları" adlı ayrı dosyalar halinde düzenlenebilir. Bkz: *önişlemci başvurusu* hakkında bilgi için [makroları](../preprocessor/macros-c-cpp.md) ve [dosyaları dahil etme](../preprocessor/hash-include-directive-c-cpp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program Yapısı](../c-language/program-structure.md)