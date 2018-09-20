---
title: -Ox (en fazla hız iyileştirmelerini etkinleştir) | Microsoft Docs
ms.custom: ''
ms.date: 09/25/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.ToolOptimization
- /ox
dev_langs:
- C++
helpviewer_keywords:
- Ox compiler option [C++]
- fast code [C++]
- /Ox compiler option [C++]
- -Ox compiler option [C++]
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e1da84c3a4ec481d3af2880a80f5923bf0c50cc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438086"
---
# <a name="ox-enable-most-speed-optimizations"></a>/Ox (en fazla hız iyileştirmelerini etkinleştir)

**/Ox** hızına iyileştirme birleşimi derleyici seçeneği sağlar. Visual Studio IDE ve derleyici yardım iletisini bazı sürümlerinde bu adlandırılır *tam iyileştirme*, ancak **/Ox** derleyici seçeneği yalnızca bir alt kümesi etkinleştirilir hızını en iyi duruma getirme seçenekleri sağlar **/O2**.

## <a name="syntax"></a>Sözdizimi

> /Ox

## <a name="remarks"></a>Açıklamalar

**/Ox** derleyici seçeneğini etkinleştirir **/O** hıza öncelik o derleyici seçenekleri. **/Ox** derleyici seçeneği ek içermez [/GF (yinelenen dizeleri ortadan)](../../build/reference/gf-eliminate-duplicate-strings.md) ve [/Gy (işlev düzeyi bağlamayı etkinleştir)](../../build/reference/gy-enable-function-level-linking.md) tarafındanetkinseçenekleri[/O1 veya/O2 (boyutu en aza indir, hızı en)](../../build/reference/o1-o2-minimize-size-maximize-speed.md). Tarafından uygulanan ek seçenekler **/O1** ve **/O2** işaretçileri dizeler ya da bir hedef adresi, hata ayıklama etkileyebilir ve katı olan dili uyumluluğu paylaşmak için işlevleri neden olabilir. **/Ox** seçenektir olmadan dahil olmak üzere, en iyileştirmelerini Etkinleştir için kolay bir yol **/GF** ve **/Gy**. Daha fazla bilgi için bkz: açıklamalarını [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) ve [/Gy](../../build/reference/gy-enable-function-level-linking.md) seçenekleri.

**/Ox** derleyici seçeneği ile aynıdır birlikte aşağıdaki seçenekleri kullanarak:

- [/OB (satır içi işlev genişletmesi)](../../build/reference/ob-inline-function-expansion.md), seçenek parametresinin 2 olduğu (**/ob2**)

- [/Og (Global İyileştirmeler)](../../build/reference/og-global-optimizations.md)

- [/Oi (İç İşlevler Üret)](../../build/reference/oi-generate-intrinsic-functions.md)

- [/Ot (hızlı koda ayrıcalık)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)

- [/Oy (Çerçeve işaretçisini atlama)](../../build/reference/oy-frame-pointer-omission.md)

**/Ox** gelen birbirini dışlar:

- [/ O1 (boyutu en aza indir)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)

- [/ O2 (hızını en üst düzeye)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)

- [/Od (Devre Dışı Bırak (Hata Ayıkla))](../../build/reference/od-disable-debug.md)

Sapma hızına yönelik iptal edebilirsiniz **/Ox** belirtirseniz derleyici seçeneği **/Oxs**, hangi birleştirir **/Ox** derleyici seçeneğiyle [/Os (ayrıcalık küçük Kod)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md). Birleşik seçenekler ayrıcalık tanı daha küçük kod boyutu.

Yayın derlemeleri için tüm kullanılabilir dosya düzeyinde iyileştirme uygulamak için belirttiğiniz öneririz [/O2 (hız en üst düzeye)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) yerine **/Ox**, ve [/O1 (boyutu en aza)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) yerine ' ın **/Oxs**. Daha da fazla iyileştirme sürüm yapıları için de göz önünde bulundurmanız [/GL (bütün Program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md) derleyici seçeneği ve [/LTCG (bağlama zamanı kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md) bağlayıcı seçeneği.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Altında **yapılandırma özellikleri**açın **C/C++** seçip **iyileştirme** özellik sayfası.

1. Değiştirme **iyileştirme** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/O Seçenekler (Kodu İyileştir)](../../build/reference/o-options-optimize-code.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)