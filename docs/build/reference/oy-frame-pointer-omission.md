---
title: /Oy (Çerçeve İşaretçisini Atlama)
ms.date: 11/19/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.OmitFramePointers
- /oy
helpviewer_keywords:
- omit frame pointer
- Oy compiler option [C++]
- stack frame pointer compiler option [C++]
- -Oy compiler option [C++]
- frame pointer omission compiler option [C++]
- suppress frame pointer creation
- /Oy compiler option [C++]
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
ms.openlocfilehash: 7884f52cc22766c6b1a864fc01abcd73f92cfabb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319973"
---
# <a name="oy-frame-pointer-omission"></a>/Oy (Çerçeve İşaretçisini Atlama)

Çağrı yığınında çerçeve işaretçilerinin oluşturulmasını engeller.

## <a name="syntax"></a>Sözdizimi

> /Oy [-]

## <a name="remarks"></a>Açıklamalar

Bu seçenek, hiçbir çerçeve işaretçisinin ayarlanması ve kaldırılması gerekmeyeceği için işlev çağrılarını hızlandırır. Genel kullanım için daha fazla kaydı serbest bırakır.

**/Oy** çerçeve işaretçisini atlamayı etkinleştirir ve **/Oy-** atlamayı devre dışı bırakır. X64, derleyiciler, **/Oy** ve **/Oy-** kullanılabilir değil.

Belirtebileceğiniz kodunuzu çerçeve tabanlı adresleme gerektiriyorsa **/Oy-** sonra seçeneği **/Ox** seçeneğini veya kullanın [en iyi duruma getirme](../../preprocessor/optimize.md) ile "**y**"ve **kapalı** çerçeve tabanlı adresleme ile en fazla iyileştirme elde etmek için bağımsız değişkenler. Derleyici burada çerçeve tabanlı adresleme gerekli olduğu çoğu durumu algılar (örneğin, ile `_alloca` ve `setjmp` işlevleri ve yapılandırılmış özel durum işleme ile).

[/Ox (etkinleştirme en hız iyileştirmelerini)](ox-full-optimization.md) ve [/O1, / O2 (boyutu en aza indirmek, hızı en üst düzeye)](o1-o2-minimize-size-maximize-speed.md) seçenekleri yaptığından **/Oy**. Belirtme **/Oy-** sonra **/Ox**, **/O1**, veya **/O2** seçeneği devre dışı bırakır **/Oy**, olduğunu açık veya zımni.

**/Oy** derleyicinin çerçeve işaretçisi bilgilerini engellemesidir çünkü daha zor hata ayıklayıcıyı kullanma derleyici seçeneği sağlar. Debug derleyici seçeneği belirtirseniz ([/z7, / zi, /zı](z7-zi-zi-debug-information-format.md)), belirttiğiniz öneririz **/Oy-** seçeneğinden sonra başka bir iyileştirme derleyici seçenekleri.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **iyileştirme** özellik sayfası.

1. Değiştirme **çerçeve işaretçilerini atla** özelliği. Bu özellik ekler veya kaldırır yalnızca **/Oy** seçeneği. Eklemek istiyorsanız **/Oy-** seçeneği için **komut satırı** özellik sayfasında ve değiştirme **ek seçenekler**.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/O Seçenekler (Kodu İyileştir)](o-options-optimize-code.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
