---
description: Daha fazla bilgi edinin:/oy (çerçeve Işaretçisi atlama)
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
ms.openlocfilehash: dc0f9272bce5ad36840eac9ccdfc7e2465f7e3c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226304"
---
# <a name="oy-frame-pointer-omission"></a>/Oy (Çerçeve İşaretçisini Atlama)

Çağrı yığınında çerçeve işaretçilerinin oluşturulmasını engeller.

## <a name="syntax"></a>Syntax

> /Oy [-]

## <a name="remarks"></a>Açıklamalar

Bu seçenek, hiçbir çerçeve işaretçisinin ayarlanması ve kaldırılması gerekmeyeceği için işlev çağrılarını hızlandırır. Ayrıca, genel kullanım için bir veya daha fazla kayıt bırakır.

**/Oy** , çerçeve işaretçisi atlanmalarını ve **/oy-** atlanması devre dışı bırakır. X64 derleyicileri, **/oy** ve **/oy-** kullanılabilir değildir.

Kodunuz çerçeve tabanlı adresleme gerektiriyorsa, **/Ox** seçeneğinden sonra **/oy-** seçeneğini belirtebilir veya çerçeve tabanlı adreslemeye en fazla iyileştirmeyi kazanmak için "**y**" ve **kapalı** bağımsız değişkenlerle [en iyi duruma getirmeyi](../../preprocessor/optimize.md) kullanabilirsiniz. Derleyici, çerçeve tabanlı adresleme 'nin gerekli olduğu çoğu durumu algılar (örneğin, `_alloca` ve `setjmp` işlevleri ile ve yapılandırılmış özel durum işlemesi ile).

[/Ox (çoğu hız Iyileştirmelerini etkinleştir)](ox-full-optimization.md) ve [/O1,/O2 (boyutu en aza Indir, en yüksek hız)](o1-o2-minimize-size-maximize-speed.md) seçenekleri **/oy**. /Ox, **/O1** veya **/O2** **seçeneği belirtildiğinde,** açık veya örtük olsun, **/oy** öğesini devre dışı bırakır. 

Derleyici çerçeve işaretçisi bilgilerini bastırdığı için **/oy** derleyici seçeneği, hata ayıklayıcıyı daha zor hale getirir. Hata ayıklama derleyicisi seçeneğini belirtirseniz ([/Z7,/Zi,/Zi](z7-zi-zi-debug-information-format.md)), herhangi bir diğer iyileştirme derleyici seçeneğinden sonra **/oy-** seçeneğini belirtmenizi öneririz.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **iyileştirme** özellik sayfasını seçin.

1. **Çerçeve Işaretçilerini atla** özelliğini değiştirin. Bu özellik yalnızca **/oy** seçeneğini ekler veya kaldırır. **/Oy-** seçeneğini eklemek Istiyorsanız, **komut satırı** özellik sayfasını seçin ve **ek seçenekleri** değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/O seçenekler (kodu Iyileştirme)](o-options-optimize-code.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
