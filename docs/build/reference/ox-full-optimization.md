---
title: "-Ox (çoğu hızı en iyi duruma getirme etkinleştir) | Microsoft Docs"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.ToolOptimization
- /ox
dev_langs: C++
helpviewer_keywords:
- Ox compiler option [C++]
- fast code [C++]
- /Ox compiler option [C++]
- -Ox compiler option [C++]
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 30794416ea166f6e41d8c0de81ef7812c7b71c31
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ox-enable-most-speed-optimizations"></a>/Ox (çoğu hızı en iyi duruma getirme etkinleştir)

**/Ox** derleyici seçeneği hızı favor iyileştirmeler bileşimini sağlar. Visual Studio IDE ve derleyici Yardım iletisi bazı sürümlerinde bu adlandırılır *tam iyileştirme*, ancak **/Ox** derleyici seçeneği yalnızca bir alt kümesini hızı en iyi duruma getirme seçenekleri tarafından etkinleştirilmiş sağlar **O2**.

## <a name="syntax"></a>Sözdizimi

> /Ox

## <a name="remarks"></a>Açıklamalar

**/Ox** derleyici seçeneği etkinleştirir **/O** derleyici seçenekleri bu ayrıcalık hızı. **/Ox** derleyici seçeneği ek içermez [/GF (yinelenen dizeleri ortadan)](../../build/reference/gf-eliminate-duplicate-strings.md) ve [/Gy (işlev düzeyi bağlamayı etkinleştir)](../../build/reference/gy-enable-function-level-linking.md) tarafındanetkinseçenekleri[/O1 veya O2 (boyutu en aza indir, hızı en üst düzeye)](../../build/reference/o1-o2-minimize-size-maximize-speed.md). Tarafından uygulanan ek seçenekleri **/O1** ve **O2** işaretçileri dizeleri veya bir hata ayıklama etkileyebilir hedef adres ve kesin dil uygunluk paylaşmak için işlevleri neden olabilir. **/Ox** seçeneği eklemeden çoğu iyileştirmeler etkinleştirmek için kolay bir yolu olmadığını **/GF** ve **/Gy**. Daha fazla bilgi için bkz: açıklamalarını [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) ve [/Gy](../../build/reference/gy-enable-function-level-linking.md) seçenekleri.

**/Ox** derleyici seçeneği aynıdır birlikte şu seçenekler kullanılarak:

- [/OB (satır içi işlev genişletmesi)](../../build/reference/ob-inline-function-expansion.md), seçenek parametresinin 2 olduğu (**/Ob2**)

- [/Og (global iyileştirmeler)](../../build/reference/og-global-optimizations.md)

- [/Oi (iç işlevler üret)](../../build/reference/oi-generate-intrinsic-functions.md)

- [/Ot (hızlı koda)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)

- [/Oy (Çerçeve işaretçisini atlama)](../../build/reference/oy-frame-pointer-omission.md)

**/Ox** gelen birbirini dışlayan olan:

- [/ O1 (boyutu en aza)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)

- [/ O2 (hızı en üst düzeye)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)

- [/Od (devre dışı bırak (Hata Ayıkla))](../../build/reference/od-disable-debug.md)

Hızına doğru sapması iptal edebilirsiniz **/Ox** belirtirseniz derleyici seçeneği **/Oxs**, hangi birleştirir **/Ox** derleyici seçeneği ile [/Os (ayrıcalık küçük Kodu)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md). Birleşik seçenekleri küçük kod boyutu favor.

Yayın derlemeleri için tüm kullanılabilir dosya düzeyinde iyileştirmeler uygulamak için belirttiğiniz öneririz [O2 (en üst düzeye hız)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) yerine **/Ox**, ve [/O1 (boyutu en aza)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) yerine **/Oxs**. Daha fazla iyileştirme sürümdeki derlemeler için de göz önüne [/GL (bütün Program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md) derleyici seçeneği ve [/LTCG (bağlama zamanı kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md) bağlayıcı seçeneği.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Altında **yapılandırma özellikleri**, açık **C/C++** ve ardından **en iyi duruma getirme** özellik sayfası.

1. Değiştirme **en iyi duruma getirme** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/O seçenekler (kodu İyileştir)](../../build/reference/o-options-optimize-code.md)  
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)