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
ms.openlocfilehash: 565cfd509e48b012581ecd6243507c60810338b9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596904"
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>/O1, /O2 (Boyutu En Aza İndir, Hızı En Yükseğe Çıkart)

Önceden tanımlanmış bir dizi boyutu etkileyen seçeneği ve oluşturulan kod hızına seçer.

## <a name="syntax"></a>Sözdizimi

> / O1, / O2

## <a name="remarks"></a>Açıklamalar

**/O1** ve **/O2** derleyici seçenekleri aynı anda birden fazla özel İyileştirme seçeneklerini ayarlamak için hızlı bir yol olan. **/O1** seçenek çoğu durumda en küçük kod oluşturan bireysel iyileştirme seçenekleri ayarlar. **/O2** seçenek çoğu durumda en hızlı kodu oluşturma seçeneklerini ayarlar. **/O2** sürüm yapıları için varsayılan seçenektir. Bu tablo tarafından ayarlanan belirli seçenekleri gösterir **/O1** ve **/O2**:

|Seçenek|Eşdeğerdir|
|------------|-------------------|
|**/ O1** (boyutu en aza indir)|[/Og](../../build/reference/og-global-optimizations.md) [/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) [/Oy](../../build/reference/oy-frame-pointer-omission.md) [/ob2](../../build/reference/ob-inline-function-expansion.md) [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) [/Gy](../../build/reference/gy-enable-function-level-linking.md)|
|**/ O2** (hızını en üst düzeye)|[/Og](../../build/reference/og-global-optimizations.md) [/Oi](../../build/reference/oi-generate-intrinsic-functions.md) [/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) [/Oy](../../build/reference/oy-frame-pointer-omission.md) [/ob2](../../build/reference/ob-inline-function-expansion.md) [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) [/Gy](../../build/reference/gy-enable-function-level-linking.md)|

**/ O1** ve **/O2** karşılıklı olarak birbirini dışlar.

> [!NOTE]
> **x86 belirli** çerçeve işaretçisini atlama kullanımını bu seçenekleri belirtir ([/Oy](../../build/reference/oy-frame-pointer-omission.md)) seçeneği.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Altında **yapılandırma özellikleri**açın **C/C++** seçip **iyileştirme** özellik sayfası.

1. Değiştirme **iyileştirme** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/O Seçenekler (Kodu İyileştir)](../../build/reference/o-options-optimize-code.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[/EH (Özel Durum İşleme Modeli)](../../build/reference/eh-exception-handling-model.md)
