---
title: /Gw (Genel Verileri En İyileştir)
ms.date: 11/04/2016
f1_keywords:
- /Gw
helpviewer_keywords:
- /Gw compiler option [C++]
- -Gw compiler option [C++]
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
ms.openlocfilehash: 406b1577b77f056e18753db10bae5675febe879e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506697"
---
# <a name="gw-optimize-global-data"></a>/Gw (Genel Verileri En İyileştir)

COMDAT bölümleri için en iyi duruma getirme genel veri paketi.

## <a name="syntax"></a>Sözdizimi

```
/Gw[-]
```

## <a name="remarks"></a>Açıklamalar

**/Gw** seçeneği COMDAT bölümleri tek tek Paket genel veri derleyicinin neden olur. Varsayılan olarak, **/Gw** kapalıdır ve açıkça etkinleştirilmesi gerekir. Açıkça devre dışı bırakmak için kullanın **/Gw-**. Her ikisi de **/Gw** ve [/GL](../../build/reference/gl-whole-program-optimization.md) olan etkin bağlayıcı bütün program iyileştirmesi COMDAT bölümler arasında birden çok nesne dosyaları başvurulmayan genel verileri dışlamak için veya birleştirmek için karşılaştırılacak kullanır aynı salt okunur genel veriler. Bu, sonuçta elde edilen ikili yürütülebilir boyutunu önemli ölçüde azaltabilir.

Derleme ve ayrı ayrı bağlantı kullanabilirsiniz [/OPT: ref](../../build/reference/opt-optimizations.md) bağlayıcı seçeneği ile derlenmiş nesne dosyaları başvurulmayan genel verilerde yürütülebilir dışlanacak **/Gw** seçeneği.

Ayrıca [/OPT: ICF](../../build/reference/opt-optimizations.md) ve [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) herhangi aynı salt okunur genel verilerde birden çok nesne dosyaları ile derlenmiş çalıştırılabilir dosyada birleştirmek için bağlayıcı seçenekleri **/Gw** seçeneği.

Daha fazla bilgi için [/Gw derleyici anahtarı ile tanışın](http://blogs.msdn.com/b/vcblog/archive/2013/09/11/introducing-gw-compiler-switch.aspx) Visual C++ Team blogunda.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **C/C++** klasör.

1. Seçin **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/Gw** seçip **Tamam**.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)