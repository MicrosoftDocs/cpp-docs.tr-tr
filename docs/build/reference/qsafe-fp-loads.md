---
title: /Qsafe_fp_loads
ms.date: 01/24/2018
ms.openlocfilehash: 57aece79dfab617121371e0489aa80f18e143372
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2019
ms.locfileid: "57819700"
---
# <a name="qsafefploads"></a>/Qsafe_fp_loads

Kayan nokta değerleri için tamsayı taşıma yönergelerini gerektirir ve belirli kayan nokta yükleme iyileştirmelerini devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

> **/Qsafe_fp_loads**

## <a name="remarks"></a>Açıklamalar

**/ Qsafe_fp_loads** yalnızca derleyicilerde kullanılabilir x86 hedef; x64 veya ARM hedefleyen derleyicilerde kullanılabilir değil.

**/ Qsafe_fp_loads** zorlar, derleyicinin bellek ile MMX arasında veri taşımak için kayan nokta taşıma yönergeler yerine tamsayı taşıma yönergelerini kullanmasını kaydeder. Bu seçenek ayrıca kayıt yük iyileştirme değeri bir özel durum yüküne neden olabilir, birden çok denetim yollarında yüklenebilir kayan nokta değerleri için devre dışı bırakır; Örneğin, bir NaN değerini.

Bu seçeneği tarafından geçersiz kılınır [/FP: except](fp-specify-floating-point-behavior.md). **/ Qsafe_fp_loads** tarafından belirtilen derleyici davranışı kümesini belirtir **/FP: except**.

**/ Qsafe_fp_loads** ile uyumsuz [/CLR](clr-common-language-runtime-compilation.md) ve [Fast](fp-specify-floating-point-behavior.md). Kayan nokta derleyici seçenekleri hakkında daha fazla bilgi için bkz. [FP (Floating-Point davranışını belirtin)](fp-specify-floating-point-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Derleyici seçeneğini girin **ek seçenekler** kutusu. Seçin **Tamam** değişikliği uygulamak için.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q Seçenekler (Düşük Düzey İşlemler)](q-options-low-level-operations.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
