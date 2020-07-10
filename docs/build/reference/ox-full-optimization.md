---
title: /Ox (çoğu hız Iyileştirmelerini etkinleştir)
description: MSVC/Ox seçeneği, tek bir seçeneğe hız için bazı derleyici iyileştirme seçeneklerini birleştirir.
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.ToolOptimization
- /Ox
- /Oxs
helpviewer_keywords:
- Ox compiler option [C++]
- fast code [C++]
- /Ox compiler option [C++]
- -Ox compiler option [C++]
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
ms.openlocfilehash: 10893fe1cf032f2ab56f27aa4af95b050c2ec37e
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180844"
---
# <a name="ox-enable-most-speed-optimizations"></a>`/Ox`(Çoğu hız Iyileştirmelerini etkinleştir)

**`/Ox`** Derleyici seçeneği, hızlanmayı tercih eden iyileştirmelerin birleşimini sunar. Visual Studio IDE 'nin bazı sürümlerinde ve derleyici yardım iletisinde *tam iyileştirme*denir, ancak **`/Ox`** derleyici seçeneği tarafından etkinleştirilen hız iyileştirme seçeneklerinin yalnızca bir alt kümesini sunar **`/O2`** .

## <a name="syntax"></a>Sözdizimi

> **`/Ox`**

## <a name="remarks"></a>Açıklamalar

**`/Ox`** Derleyici seçeneği, **`/O`** hızlanmayı tercih eden derleyici seçeneklerini sunar. **`/Ox`** Derleyici seçeneği, veya tarafından etkinleştirilen ( [ `/GF` Yinelenen dizeleri ortadan kaldırma](gf-eliminate-duplicate-strings.md) ) ve [ `/Gy` (işlev düzeyi bağlamayı etkinleştir](gy-enable-function-level-linking.md) ) seçeneklerini Içermez ( [ `/O1` `/O2` boyutu en aza indirir, hızı en üst düzeye çıkar)](o1-o2-minimize-size-maximize-speed.md). Ve tarafından uygulanan ek seçenekler **`/O1`** **`/O2`** , dizelerde ve hata ayıklama ve katı dil uyumuna uyum sağlayan bir hedef adresi paylaşma işlevlerine neden olabilir. Bu **`/Ox`** seçenek, ve dahil etmeden en iyileştirmeleri etkinleştirmenin kolay bir yoludur **`/GF`** **`/Gy`** . Daha fazla bilgi için, ve seçeneklerinin açıklamalarını inceleyin [`/GF`](gf-eliminate-duplicate-strings.md) [`/Gy`](gy-enable-function-level-linking.md) .

**`/Ox`** Derleyici seçeneği, aşağıdaki seçenekleri birlikte kullanmakla aynıdır:

- [ `/Ob` (Satır Içi işlev genişletmesi)](ob-inline-function-expansion.md), burada seçenek parametresi 2 ( **`/Ob2`** )

- [`/Oi`(Iç Işlevler üret)](oi-generate-intrinsic-functions.md)

- [`/Ot`(Hızlı kodu tercih et)](os-ot-favor-small-code-favor-fast-code.md)

- [`/Oy`(Çerçeve Işaretçisi atlama)](oy-frame-pointer-omission.md)

**`/Ox`** Şu kaynaktan birbirini dışlıyor:

- [`/O1`(Boyutu en aza indir)](o1-o2-minimize-size-maximize-speed.md)

- [`/O2`(Hızı en yükseğe çıkar)](o1-o2-minimize-size-maximize-speed.md)

- [`/Od`(Devre dışı bırak (Hata Ayıkla))](od-disable-debug.md)

**`/Ox`** **`/Oxs`** **`/Ox`** Derleyici seçeneğini Ile [ `/Os` (küçük koda göre)](os-ot-favor-small-code-favor-fast-code.md)birleştiren derleyici seçeneğinin hızına doğru olan farkı iptal edebilirsiniz. Birleşik seçenekler daha küçük kod boyutunu tercih edin.  **`/Oxs`** Seçenek, **`/Ox`** **`/Os`** seçeneklerin söz konusu sırada ne zaman görünmemekle tam olarak aynı şekilde belirlenir.

Yayın yapıları için tüm kullanılabilir dosya düzeyi iyileştirmeleri uygulamak için yerine ( [ `/O2` hızı en üst düzeye çıkarın](o1-o2-minimize-size-maximize-speed.md) ) yerine **`/Ox`** ve [ `/O1` (boyutu en aza indir)](o1-o2-minimize-size-maximize-speed.md) önerilir **`/Oxs`** . Yayın yapılarında daha fazla iyileştirme için, [ `/GL` (tüm program iyileştirmesi)](gl-whole-program-optimization.md) derleyici seçeneğini ve [ `/LTCG` (bağlantı zamanı kodu oluşturma)](ltcg-link-time-code-generation.md) bağlayıcı seçeneğini de göz önünde bulundurun.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **iyileştirme** özellik sayfasını seçin.

1. **Optimizasyon** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[`/O`Seçenekler (kodu Iyileştirme)](o-options-optimize-code.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
