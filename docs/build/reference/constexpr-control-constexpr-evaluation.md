---
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
ms.openlocfilehash: 7b3ae1cd732fe1ec234e2734ea4c6fa86db9d5af
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223869"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (Constexpr değerlendirmesini denetle)

Derleme zamanında değerlendirme parametrelerini denetlemek için **/constexpr** derleyici seçeneklerini kullanın **`constexpr`** .

## <a name="syntax"></a>Sözdizimi

> **/constexpr: derinlik**<em>N</em>\
> **/constexpr: backtrace**<em>N</em>\
> **/constexpr: adım**<em>N</em>

## <a name="arguments"></a>Arguments

**derinlik**<em>n</em> özyinelemeli **`constexpr`** işlev çağırma derinliğini *N* düzeylerine göre sınırlandırın. Varsayılan değer 512 ' dir.

**backtrace**<em>n</em> tanılamalarda en fazla *N* **`constexpr`** değerlendirme gösterir. Varsayılan değer 10 ' dur.

**adım**<em>n</em> **`constexpr`** adımdan sonra değerlendirmeyi *N* sonlandırın. Varsayılan değer 100.000 ' dir.

## <a name="remarks"></a>Açıklamalar

**/Constexpr** derleyici seçenekleri, ifadelerin derleme zamanı değerlendirmesini denetler **`constexpr`** . Derleyicinin değerlendirmede çok fazla zaman harcamasını engellemek için değerlendirme adımları, özyineleme düzeyleri ve geri izleme derinliği denetlenir **`constexpr`** . Dil öğesi hakkında daha fazla bilgi için **`constexpr`** bkz. [constexpr (C++)](../../cpp/constexpr-cpp.md).

**/Constexpr** seçenekleri Visual Studio 2015 ' den başlayarak kullanılabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenizin **Özellik sayfaları** iletişim kutusunu açın.

2. **Yapılandırma özellikleri**altında **C/C++** klasörünü genişletin ve **komut satırı** özellik sayfasını seçin.

3. **Ek seçenekler** kutusuna herhangi bir **/constexpr** derleyici seçeneği girin. Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
