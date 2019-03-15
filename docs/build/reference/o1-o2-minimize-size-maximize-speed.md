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
ms.openlocfilehash: d33fe6bceae09267fd3f79ffe3dc26864e87c764
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820591"
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>/O1, /O2 (Boyutu En Aza İndir, Hızı En Yükseğe Çıkart)

Önceden tanımlanmış bir dizi boyutu etkileyen seçeneği ve oluşturulan kod hızına seçer.

## <a name="syntax"></a>Sözdizimi

> / O1, / O2

## <a name="remarks"></a>Açıklamalar

**/O1** ve **/O2** derleyici seçenekleri aynı anda birden fazla özel İyileştirme seçeneklerini ayarlamak için hızlı bir yol olan. **/O1** seçenek çoğu durumda en küçük kod oluşturan bireysel iyileştirme seçenekleri ayarlar. **/O2** seçenek çoğu durumda en hızlı kodu oluşturma seçeneklerini ayarlar. **/O2** sürüm yapıları için varsayılan seçenektir. Bu tablo tarafından ayarlanan belirli seçenekleri gösterir **/O1** ve **/O2**:

|Seçenek|Eşdeğerdir|
|------------|-------------------|
|**/ O1** (boyutu en aza indir)|[/Og](og-global-optimizations.md) [/Os](os-ot-favor-small-code-favor-fast-code.md) [/Oy](oy-frame-pointer-omission.md) [/ob2](ob-inline-function-expansion.md) [/GF](gf-eliminate-duplicate-strings.md) [/Gy](gy-enable-function-level-linking.md)|
|**/ O2** (hızını en üst düzeye)|[/Og](og-global-optimizations.md) [/Oi](oi-generate-intrinsic-functions.md) [/Ot](os-ot-favor-small-code-favor-fast-code.md) [/Oy](oy-frame-pointer-omission.md) [/ob2](ob-inline-function-expansion.md) [/GF](gf-eliminate-duplicate-strings.md) [/Gy](gy-enable-function-level-linking.md)|

**/ O1** ve **/O2** karşılıklı olarak birbirini dışlar.

> [!NOTE]
> **x86 belirli** çerçeve işaretçisini atlama kullanımını bu seçenekleri belirtir ([/Oy](oy-frame-pointer-omission.md)) seçeneği.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Altında **yapılandırma özellikleri**açın **C/C++** seçip **iyileştirme** özellik sayfası.

1. Değiştirme **iyileştirme** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/O Seçenekler (Kodu İyileştir)](o-options-optimize-code.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
[/EH (Özel Durum İşleme Modeli)](eh-exception-handling-model.md)
