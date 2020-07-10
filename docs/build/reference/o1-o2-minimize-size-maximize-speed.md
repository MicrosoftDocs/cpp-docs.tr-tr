---
title: /O1, /O2 (Boyutu En Aza İndir, Hızı En Yükseğe Çıkart)
description: MSVC derleyici seçenekleri/O1 ve/O2 en küçük boyut veya en yüksek hız için tüm iyileştirmeleri belirler.
ms.date: 07/08/2020
f1_keywords:
- /O2
- /O1
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
ms.openlocfilehash: c1eda8395e604468cbb23572ec930d6171984fe4
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180909"
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>`/O1`, `/O2` (Boyutu en aza indir, hızı Büyüt)

Oluşturulan kodun boyutunu ve hızını etkileyen önceden tanımlanmış bir seçenek kümesi seçer.

## <a name="syntax"></a>Sözdizimi

> **`/O1`**\
> **`/O2`**

## <a name="remarks"></a>Açıklamalar

**`/O1`** Ve **`/O2`** derleyici seçenekleri, aynı anda birkaç özel iyileştirme seçeneği ayarlamak için hızlı bir yoldur. **`/O1`** Seçeneği, çoğu durumda en küçük kodu oluşturan en iyi duruma getirme seçeneklerini ayarlar. **`/O2`** Seçeneği, çoğu durumda en hızlı kodu oluşturan seçenekleri ayarlar. Bu **`/O2`** seçenek, yayın derlemeleri için varsayılan seçenektir. Bu tablo, ve tarafından ayarlanan özel seçenekleri gösterir **`/O1`** **`/O2`** :

| Seçenek | Eşdeğer |
|--|--|
| **`/O1`**(Boyutu en aza indir) | [`/Og`](og-global-optimizations.md) [`/Os`](os-ot-favor-small-code-favor-fast-code.md) [`/Oy`](oy-frame-pointer-omission.md) [`/Ob2`](ob-inline-function-expansion.md) [`/GF`](gf-eliminate-duplicate-strings.md) [`/Gy`](gy-enable-function-level-linking.md) |
| **`/O2`**(Hızı en yükseğe çıkar) | [`/Og`](og-global-optimizations.md) [`/Oi`](oi-generate-intrinsic-functions.md) [`/Ot`](os-ot-favor-small-code-favor-fast-code.md) [`/Oy`](oy-frame-pointer-omission.md) [`/Ob2`](ob-inline-function-expansion.md) [`/GF`](gf-eliminate-duplicate-strings.md) [`/Gy`](gy-enable-function-level-linking.md) |

**`/O1`** ve **`/O2`** birbirini dışlıyor.

> [!NOTE]
> **x86 'e özgü**\
> Bu seçenekler, çerçeve Işaretçisi atlama ( [`/Oy`](oy-frame-pointer-omission.md) ) seçeneğinin kullanımını kapsıyor.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **iyileştirme** özellik sayfasını seçin.

1. **Optimizasyon** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[`/O`Seçenekler (kodu Iyileştirme)](o-options-optimize-code.md)<br/>
[MSVC derleyicisi seçenekleri](compiler-options.md)<br/>
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)<br/>
[`/EH`(Özel durum işleme modeli)](eh-exception-handling-model.md)
