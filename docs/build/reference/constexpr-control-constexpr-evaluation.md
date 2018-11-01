---
title: /constexpr (constexpr değerlendirmesini Denetle)
ms.date: 08/15/2017
f1_keywords:
- /constexpr
- -constexpr
helpviewer_keywords:
- /constexpr control constexpr evaluation [C++]
- -constexpr control constexpr evaluation [C++]
- constexpr control constexpr evaluation [C++]
ms.assetid: 76d56784-f5ad-401d-841d-09d1059e8b8c
ms.openlocfilehash: ea55a2686c2cdd7f4e0a6b558d3cd456fe87cb9d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544254"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (constexpr değerlendirmesini Denetle)

Kullanım **/constexpr** denetim parametreleri için derleyici seçenekleri **constexpr** derleme zamanında değerlendirme.

## <a name="syntax"></a>Sözdizimi

> **/ constexpr: Depth**<em>N</em>
>  **/constexpr: backtrace**<em>N</em>
> **Steps** <em>N</em>

## <a name="arguments"></a>Arguments

**Derinlik**<em>N</em> özyinelemeli derinliğini sınırlamak **constexpr** işlev çağrısı için *N* düzeyleri. Varsayılan değer 512'dır.

**backtrace**<em>N</em> kadar Göster *N* **constexpr** değerlendirmeleri tanılama. Varsayılan değer 10'dur.

**adımları**<em>N</em> sonlandırma **constexpr** değerlendirmesinden sonra *N* adımları. Varsayılan değer 100. 000 ' dir.

## <a name="remarks"></a>Açıklamalar

**/Constexpr** derleyici seçenekleri denetimi, derleme zamanı değerlendirmesi **constexpr** ifadeler. Derleyici, üzerinde çok fazla zaman harcama önlemek için değerlendirme adımlar, özyineleme düzeyi ve backtrace derinliği denetlenir **constexpr** değerlendirme. Daha fazla bilgi için **constexpr** dil öğesi için bkz: [constexpr (C++)](../../cpp/constexpr-cpp.md).

**/Constexpr** seçeneklerdir Visual Studio 2015'te sonraki sürümlerinde kullanılabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenizin açın **özellik sayfaları** iletişim kutusu.

2. Altında **yapılandırma özellikleri**, genişletme **C/C++** klasörü seçin **komut satırı** özellik sayfası.

3. Tüm girin **/constexpr** derleyici seçenekleri **ek seçenekler** kutusu. Seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)