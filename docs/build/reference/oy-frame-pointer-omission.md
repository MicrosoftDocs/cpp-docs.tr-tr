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
ms.openlocfilehash: 6c077b5a350d7381adc5412ca4a318713d720ad6
ms.sourcegitcommit: 1870c342d44b10990fd015e60856225c3026e8c2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2018
ms.locfileid: "49963057"
---
# <a name="oy-frame-pointer-omission"></a>/Oy (Çerçeve İşaretçisini Atlama)

Çağrı yığınında çerçeve işaretçilerinin oluşturulmasını engeller.

## <a name="syntax"></a>Sözdizimi

> /Oy [-]

## <a name="remarks"></a>Açıklamalar

Bu seçenek, hiçbir çerçeve işaretçisinin ayarlanması ve kaldırılması gerekmeyeceği için işlev çağrılarını hızlandırır. Genel kullanım için daha fazla kaydı serbest bırakır.

**/Oy** çerçeve işaretçisini atlamayı etkinleştirir ve **/Oy-** atlamayı devre dışı bırakır. **/Oy** yalnızca x86 içinde kullanılabilir derleyicileri.

Kodunuz EBP tabanlı adresleme gerektiriyorsa belirtebilmeniz için **/Oy-** sonra seçeneği **/Ox** seçeneğini veya kullanın [en iyi duruma getirme](../../preprocessor/optimize.md) ile "**y**" ve **kapalı** EBP tabanlı adresleme ile en fazla iyileştirme elde etmek için bağımsız değişkenler. Derleyici burada EBP tabanlı adresleme gerekli olduğu çoğu durumu algılar (örneğin, ile `_alloca` ve `setjmp` işlevleri ve yapılandırılmış özel durum işleme ile).

[/Ox (etkinleştirme en hız iyileştirmelerini)](../../build/reference/ox-full-optimization.md) ve [/O1, / O2 (boyutu en aza indirmek, hızı en üst düzeye)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) seçenekleri yaptığından **/Oy**. Belirtme **/Oy-** sonra **/Ox**, **/O1**, veya **/O2** seçeneği devre dışı bırakır **/Oy**, olduğunu açık veya zımni.

**/Oy** derleyicinin çerçeve işaretçisi bilgilerini engellemesidir çünkü daha zor hata ayıklayıcıyı kullanma derleyici seçeneği sağlar. Debug derleyici seçeneği belirtirseniz ([/z7, / zi, /zı](../../build/reference/z7-zi-zi-debug-information-format.md)), belirttiğiniz öneririz **/Oy-** seçeneğinden sonra başka bir iyileştirme derleyici seçenekleri.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **iyileştirme** özellik sayfası.

1. Değiştirme **çerçeve işaretçilerini atla** özelliği. Bu özellik ekler veya kaldırır yalnızca **/Oy** seçeneği. Eklemek istiyorsanız **/Oy-** seçeneğinde, tıklayın **komut satırı** ve değiştirme **ek seçenekler**.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/O Seçenekler (Kodu İyileştir)](../../build/reference/o-options-optimize-code.md)

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)

[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
