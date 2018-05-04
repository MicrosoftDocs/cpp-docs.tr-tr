---
title: -Oy (Çerçeve işaretçisini atlama) | Microsoft Docs
ms.custom: ''
ms.date: 09/22/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.OmitFramePointers
- /oy
dev_langs:
- C++
helpviewer_keywords:
- omit frame pointer
- Oy compiler option [C++]
- stack frame pointer compiler option [C++]
- -Oy compiler option [C++]
- frame pointer omission compiler option [C++]
- suppress frame pointer creation
- /Oy compiler option [C++]
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6feb682d364c4c40fd01e4aff33404c4506d9c1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="oy-frame-pointer-omission"></a>/Oy (Çerçeve İşaretçisini Atlama)

Çağrı yığınında çerçeve işaretçilerinin oluşturulmasını engeller.

## <a name="syntax"></a>Sözdizimi

> /Oy [-]

## <a name="remarks"></a>Açıklamalar

Bu seçenek, hiçbir çerçeve işaretçisinin ayarlanması ve kaldırılması gerekmeyeceği için işlev çağrılarını hızlandırır. Ayrıca, bir veya daha fazla kaydı (Intel 386 veya sonrasında EBP) sık kullanılan değişkenlerin ve alt ifadelerin saklanması için boş bırakır.

**/Oy** çerçeve işaretçisini atlama sağlar ve **/Oy-** atlandığını devre dışı bırakır. **/Oy** yalnızca x86 kullanılabilir derleyicileri.

Belirleyebileceğiniz kodunuzu EBP tabanlı adresleme gerektiriyorsa, **/Oy-** sonra seçeneği **/Ox** seçeneğini veya kullanmak [en iyi duruma getirme](../../preprocessor/optimize.md) ile "**y**" ve **kapalı** EBP tabanlı adresleme ile en fazla iyileştirmesi kazanmak için bağımsız değişkenler. Derleyici EBP tabanlı adresleme olduğu gerekli çoğu durumlar algılar (örneğin, ile `_alloca` ve `setjmp` işlevleri ve yapılandırılmış özel durum işleme ile).

[/Ox (etkinleştirmek en hızlı iyileştirmeler)](../../build/reference/ox-full-optimization.md) ve [/O1, O2 (boyutu en aza indirmek, hızı en üst düzeye)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) seçenekleri kapsıyor **/Oy**. Belirtme **/Oy-** sonra **/Ox**, **/O1**, veya **O2** seçeneği devre dışı bırakır **/Oy**, bunun açık veya zımni.

**/Oy** çünkü derleyici çerçeve işaretçisi bilgi bastırır daha zor hata ayıklayıcıyı kullanma derleyici seçeneği sağlar. Debug derleyici seçeneği belirlerseniz ([/Z7, / zi, /zı](../../build/reference/z7-zi-zi-debug-information-format.md)), belirtilmesi önerilir **/Oy-** seçeneğinden sonra başka bir iyileştirme derleyici seçenekleri.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Tıklatın **C/C++** klasör.

1. Tıklatın **en iyi duruma getirme** özellik sayfası.

1. Değiştirme **atlayın çerçeve işaretçileri** özelliği. Bu özellik ekler veya kaldırır yalnızca **/Oy** seçeneği. Eklemek istiyorsanız **/Oy-** seçeneği, tıklatın **komut satırı** ve değiştirme **ek seçenekler**.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/O Seçenekler (Kodu İyileştir)](../../build/reference/o-options-optimize-code.md)

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)

[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)