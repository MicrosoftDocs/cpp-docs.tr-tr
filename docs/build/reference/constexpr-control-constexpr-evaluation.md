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
ms.openlocfilehash: 178acc548fb9c89dcfde104d2a12d85637440e28
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294258"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (constexpr değerlendirmesini Denetle)

Kullanım **/constexpr** denetim parametreleri için derleyici seçenekleri **constexpr** derleme zamanında değerlendirme.

## <a name="syntax"></a>Sözdizimi

> **/constexpr:depth**<em>N</em>
>  **/constexpr:backtrace**<em>N</em>
>  **/constexpr:steps**<em>N</em>

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

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
