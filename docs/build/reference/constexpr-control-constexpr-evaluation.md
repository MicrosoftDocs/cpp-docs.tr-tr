---
description: Şu konuda daha fazla bilgi edinin:/constexpr (constexpr değerlendirmesini denetle)
title: /constexpr (Constexpr değerlendirmesini denetle)
ms.date: 08/15/2017
f1_keywords:
- /constexpr
- -constexpr
helpviewer_keywords:
- /constexpr control constexpr evaluation [C++]
- -constexpr control constexpr evaluation [C++]
- constexpr control constexpr evaluation [C++]
ms.assetid: 76d56784-f5ad-401d-841d-09d1059e8b8c
ms.openlocfilehash: a9274321933fb0fbcf965943b0168db85c8a8d5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205349"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (Constexpr değerlendirmesini denetle)

Derleme zamanında değerlendirme parametrelerini denetlemek için **/constexpr** derleyici seçeneklerini kullanın **`constexpr`** .

## <a name="syntax"></a>Syntax

> **/constexpr: derinlik**<em>N</em>\
> **/constexpr: backtrace**<em>N</em>\
> **/constexpr: adım**<em>N</em>

## <a name="arguments"></a>Arguments

**derinlik**<em>n</em> özyinelemeli **`constexpr`** işlev çağırma derinliğini *N* düzeylerine göre sınırlandırın. Varsayılan değer 512 ' dir.

**backtrace**<em>n</em> tanılamalarda en fazla *N* **`constexpr`** değerlendirme gösterir. Varsayılan değer 10 ' dur.

**adım**<em>n</em> **`constexpr`** adımdan sonra değerlendirmeyi  sonlandırın. Varsayılan değer 100.000 ' dir.

## <a name="remarks"></a>Açıklamalar

**/Constexpr** derleyici seçenekleri, ifadelerin derleme zamanı değerlendirmesini denetler **`constexpr`** . Derleyicinin değerlendirmede çok fazla zaman harcamasını engellemek için değerlendirme adımları, özyineleme düzeyleri ve geri izleme derinliği denetlenir **`constexpr`** . Dil öğesi hakkında daha fazla bilgi için **`constexpr`** bkz. [constexpr (C++)](../../cpp/constexpr-cpp.md).

**/Constexpr** seçenekleri Visual Studio 2015 ' den başlayarak kullanılabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenizin **Özellik sayfaları** iletişim kutusunu açın.

2. **Yapılandırma özellikleri** altında **C/C++** klasörünü genişletin ve **komut satırı** özellik sayfasını seçin.

3. **Ek seçenekler** kutusuna herhangi bir **/constexpr** derleyici seçeneği girin. Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
