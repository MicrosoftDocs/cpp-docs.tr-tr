---
title: /Ox (en fazla hız iyileştirmelerini etkinleştir)
ms.date: 10/18/2018
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
ms.openlocfilehash: e39905608087425fe5a445f4ef88434d73bb2ded
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320103"
---
# <a name="ox-enable-most-speed-optimizations"></a>/Ox (en fazla hız iyileştirmelerini etkinleştir)

**/Ox** hızına iyileştirme birleşimi derleyici seçeneği sağlar. Visual Studio IDE ve derleyici yardım iletisini bazı sürümlerinde bu adlandırılır *tam iyileştirme*, ancak **/Ox** derleyici seçeneği yalnızca bir alt kümesi etkinleştirilir hızını en iyi duruma getirme seçenekleri sağlar **/O2**.

## <a name="syntax"></a>Sözdizimi

> **/Ox**

## <a name="remarks"></a>Açıklamalar

**/Ox** derleyici seçeneğini etkinleştirir **/O** hıza öncelik o derleyici seçenekleri. **/Ox** derleyici seçeneği ek içermez [/GF (yinelenen dizeleri ortadan)](gf-eliminate-duplicate-strings.md) ve [/Gy (işlev düzeyi bağlamayı etkinleştir)](gy-enable-function-level-linking.md) tarafındanetkinseçenekleri[/O1 veya/O2 (boyutu en aza indir, hızı en)](o1-o2-minimize-size-maximize-speed.md). Tarafından uygulanan ek seçenekler **/O1** ve **/O2** işaretçileri dizeler ya da bir hedef adresi, hata ayıklama etkileyebilir ve katı olan dili uyumluluğu paylaşmak için işlevleri neden olabilir. **/Ox** seçenektir olmadan dahil olmak üzere, en iyileştirmelerini Etkinleştir için kolay bir yol **/GF** ve **/Gy**. Daha fazla bilgi için bkz: açıklamalarını [/GF](gf-eliminate-duplicate-strings.md) ve [/Gy](gy-enable-function-level-linking.md) seçenekleri.

**/Ox** derleyici seçeneği ile aynıdır birlikte aşağıdaki seçenekleri kullanarak:

- [/OB (satır içi işlev genişletmesi)](ob-inline-function-expansion.md), seçenek parametresinin 2 olduğu (**/ob2**)

- [/Og (Global İyileştirmeler)](og-global-optimizations.md)

- [/Oi (İç İşlevler Üret)](oi-generate-intrinsic-functions.md)

- [/Ot (hızlı koda ayrıcalık)](os-ot-favor-small-code-favor-fast-code.md)

- [/Oy (Çerçeve işaretçisini atlama)](oy-frame-pointer-omission.md)

**/Ox** gelen birbirini dışlar:

- [/ O1 (boyutu en aza indir)](o1-o2-minimize-size-maximize-speed.md)

- [/ O2 (hızını en üst düzeye)](o1-o2-minimize-size-maximize-speed.md)

- [/Od (Devre Dışı Bırak (Hata Ayıkla))](od-disable-debug.md)

Sapma hızına yönelik iptal edebilirsiniz **/Ox** belirtirseniz derleyici seçeneği **/Oxs**, hangi birleştirir **/Ox** derleyici seçeneğiyle [/Os (ayrıcalık küçük Kod)](os-ot-favor-small-code-favor-fast-code.md). Birleşik seçenekler ayrıcalık tanı daha küçük kod boyutu.  **/Oxs** seçenek, tam olarak belirterek aynı **/Ox** **/Os** seçenekler, sırasıyla görüntülenirken.

Yayın derlemeleri için tüm kullanılabilir dosya düzeyinde iyileştirme uygulamak için belirttiğiniz öneririz [/O2 (hız en üst düzeye)](o1-o2-minimize-size-maximize-speed.md) yerine **/Ox**, ve [/O1 (boyutu en aza)](o1-o2-minimize-size-maximize-speed.md) yerine ' ın **/Oxs**. Daha da fazla iyileştirme sürüm yapıları için de göz önünde bulundurmanız [/GL (bütün Program iyileştirmesi)](gl-whole-program-optimization.md) derleyici seçeneği ve [/LTCG (bağlama zamanı kodu oluşturma)](ltcg-link-time-code-generation.md) bağlayıcı seçeneği.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Altında **yapılandırma özellikleri**açın **C/C++** seçip **iyileştirme** özellik sayfası.

1. Değiştirme **iyileştirme** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/O Seçenekler (Kodu İyileştir)](o-options-optimize-code.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
