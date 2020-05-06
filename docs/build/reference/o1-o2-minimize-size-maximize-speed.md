---
title: /O1, /O2 (Boyutu En Aza İndir, Hızı En Yükseğe Çıkart)
ms.date: 09/25/2017
f1_keywords:
- /o2
- /o1
helpviewer_keywords:
- maximize speed compiler option [C++]
- minimize size compiler option [C++]
- -O2 compiler option [C++]
- fast code
- small code
- O2 compiler option [C++]
- /O2 compiler option [C++]
- -O1 compiler option [C++]
- O1 compiler option [C++]
- /O1 compiler option [C++]
ms.assetid: 2d1423f5-53d9-44da-8908-b33a351656c2
ms.openlocfilehash: 3daf5dd5f9912194fd5d8aaeb4c7a312be142b69
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825357"
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>/O1, /O2 (Boyutu En Aza İndir, Hızı En Yükseğe Çıkart)

Oluşturulan kodun boyutunu ve hızını etkileyen önceden tanımlanmış bir seçenek kümesi seçer.

## <a name="syntax"></a>Sözdizimi

> O1
> /O2

## <a name="remarks"></a>Açıklamalar

**/O1** ve **/O2** derleyici seçenekleri, aynı anda birkaç özel iyileştirme seçeneği ayarlamak için hızlı bir yoldur. **/O1** seçeneği, çoğu durumda en küçük kodu oluşturan en iyi duruma getirme seçeneklerini ayarlar. **/O2** seçeneği, çoğu durumda en hızlı kodu oluşturan seçenekleri ayarlar. **/O2** seçeneği yayın derlemeleri için varsayılan seçenektir. Bu tablo, **/O1** ve **/O2**tarafından ayarlanan özel seçenekleri gösterir:

|Seçenek|Eşdeğer|
|------------|-------------------|
|**/O1** (boyutu en aza indir)|[/OG](og-global-optimizations.md) [/OS](os-ot-favor-small-code-favor-fast-code.md) [/oy](oy-frame-pointer-omission.md) [/Ob2](ob-inline-function-expansion.md) [/GF](gf-eliminate-duplicate-strings.md) [/GY](gy-enable-function-level-linking.md)|
|**/O2** (hızı en yükseğe çıkar)|[/OG](og-global-optimizations.md) [/Oi](oi-generate-intrinsic-functions.md) [/ot](os-ot-favor-small-code-favor-fast-code.md) [/oy](oy-frame-pointer-omission.md) [/Ob2](ob-inline-function-expansion.md) [/GF](gf-eliminate-duplicate-strings.md) [/GY](gy-enable-function-level-linking.md)|

**/O1** ve **/O2** birbirini dışlıyor.

> [!NOTE]
> **x86 özgü**\
> Bu seçenekler çerçeve Işaretçisi atlama ([/oy](oy-frame-pointer-omission.md)) seçeneğinin kullanımını kapsıyor.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**altında **C/C++** ' ı açın ve ardından **iyileştirme** özellik sayfasını seçin.

1. **Optimizasyon** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/O Seçenekler (Kodu İyileştir)](o-options-optimize-code.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[/EH (özel durum Işleme modeli)](eh-exception-handling-model.md)
