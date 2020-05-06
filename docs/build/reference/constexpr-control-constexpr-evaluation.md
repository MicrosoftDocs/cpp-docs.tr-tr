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
ms.openlocfilehash: 4d3f33a64dcebfc40778f81354cb5067a5239ace
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825597"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (Constexpr değerlendirmesini denetle)

Derleme zamanında **constexpr** değerlendirmesinin parametrelerini denetlemek için **/constexpr** derleyici seçeneklerini kullanın.

## <a name="syntax"></a>Sözdizimi

> **/constexpr: derinlik**<em>N</em>\
> **/constexpr: backtrace**<em>N</em>\
> **/constexpr: adım**<em>N</em>

## <a name="arguments"></a>Bağımsız Değişkenler

**derinlik**<em>n</em> özyinelemeli **constexpr** işlevi çağırma derinliğini *N* düzeylere sınırlayın. Varsayılan değer 512 ' dir.

**backtrace**<em>n</em> tanılamalarda en fazla *N* **constexpr** değerlendirmesi görüntüleyin. Varsayılan değer 10 ' dur.

**adım**<em>n adımdan</em> sonra **constexpr** değerlendirmesini *N* sonlandırın. Varsayılan değer 100.000 ' dir.

## <a name="remarks"></a>Açıklamalar

**/Constexpr** derleyici seçenekleri, **constexpr** ifadelerinin derleme zamanı değerlendirmesini denetler. Derleyicinin **constexpr** değerlendirmesinde çok fazla zaman harcamasını engellemek için değerlendirme adımları, özyineleme düzeyleri ve geri izleme derinliği denetlenir. **Constexpr** dil öğesi hakkında daha fazla bilgi için bkz. [constexpr (C++)](../../cpp/constexpr-cpp.md).

**/Constexpr** seçenekleri Visual Studio 2015 ' den başlayarak kullanılabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenizin **Özellik sayfaları** iletişim kutusunu açın.

2. **Yapılandırma özellikleri**altında **C/C++** klasörünü genişletin ve **komut satırı** özellik sayfasını seçin.

3. **Ek seçenekler** kutusuna herhangi bir **/constexpr** derleyici seçeneği girin. Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
