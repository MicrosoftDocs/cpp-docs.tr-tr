---
title: /Qsafe_fp_loads
ms.date: 01/24/2018
ms.openlocfilehash: e1ef4237fe3af39e76777609a06f90bd585ca422
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504445"
---
# <a name="qsafefploads"></a>/Qsafe_fp_loads

Kayan nokta değerleri için tamsayı taşıma yönergelerini gerektirir ve belirli kayan nokta yükleme iyileştirmelerini devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

> **/Qsafe_fp_loads**

## <a name="remarks"></a>Açıklamalar

**/ Qsafe_fp_loads** yalnızca derleyicilerde kullanılabilir x86 hedef; x64 veya ARM hedefleyen derleyicilerde kullanılabilir değil.

**/ Qsafe_fp_loads** zorlar, derleyicinin bellek ile MMX arasında veri taşımak için kayan nokta taşıma yönergeler yerine tamsayı taşıma yönergelerini kullanmasını kaydeder. Bu seçenek ayrıca kayıt yük iyileştirme değeri bir özel durum yüküne neden olabilir, birden çok denetim yollarında yüklenebilir kayan nokta değerleri için devre dışı bırakır; Örneğin, bir NaN değerini.

Bu seçeneği tarafından geçersiz kılınır [/FP: except](../../build/reference/fp-specify-floating-point-behavior.md). **/ Qsafe_fp_loads** tarafından belirtilen derleyici davranışı kümesini belirtir **/FP: except**.

**/ Qsafe_fp_loads** ile uyumsuz [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) ve [Fast](../../build/reference/fp-specify-floating-point-behavior.md). Kayan nokta derleyici seçenekleri hakkında daha fazla bilgi için bkz. [FP (Floating-Point davranışını belirtin)](../../build/reference/fp-specify-floating-point-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Derleyici seçeneğini girin **ek seçenekler** kutusu. Seçin **Tamam** değişikliği uygulamak için.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q Seçenekler (Düşük Düzey İşlemler)](../../build/reference/q-options-low-level-operations.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
