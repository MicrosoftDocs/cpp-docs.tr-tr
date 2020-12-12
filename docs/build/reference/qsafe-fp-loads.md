---
description: Hakkında daha fazla bilgi edinin:/Qsafe_fp_loads
title: /Qsafe_fp_loads
ms.date: 01/24/2018
ms.openlocfilehash: e569b308d2da982c72775699ff2149daa45a8f2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225524"
---
# <a name="qsafe_fp_loads"></a>/Qsafe_fp_loads

Kayan nokta değerleri için tamsayı taşıma yönergeleri gerektirir ve belirli kayan nokta yükleme iyileştirmelerini devre dışı bırakır.

## <a name="syntax"></a>Syntax

> **/Qsafe_fp_loads**

## <a name="remarks"></a>Açıklamalar

**/Qsafe_fp_loads** yalnızca x86 'yi hedefleyen derleyicilerde kullanılabilir; x64 veya ARM 'yi hedefleyen derleyicilerde kullanılamaz.

**/Qsafe_fp_loads** derleyiciyi, verileri bellek ve MMX kayıtları arasında taşımak için kayan nokta taşıma yönergeleri yerine tamsayı taşıma yönergeleri kullanmak üzere zorlar. Bu seçenek ayrıca, değer yüklemede bir özel duruma neden olabileceği zaman birden fazla denetim yoluna yüklenebilen kayan nokta değerleri için yükleme iyileştirmesi kaydetmeyi devre dışı bırakır — Örneğin, bir NaN değeri.

Bu seçenek [/FP: except](fp-specify-floating-point-behavior.md)tarafından geçersiz kılınır. **/Qsafe_fp_loads** **/FP: except** tarafından belirtilen derleyici davranışının bir alt kümesini belirtir.

**/Qsafe_fp_loads** [/clr](clr-common-language-runtime-compilation.md) ve [/FP: Fast](fp-specify-floating-point-behavior.md)ile uyumsuzdur. Kayan nokta derleyicisi seçenekleri hakkında daha fazla bilgi için bkz. [/FP (Floating-Point davranışını belirt)](fp-specify-floating-point-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** kutusunda derleyici seçeneğini girin. Değişikliği uygulamak için **Tamam ' ı** seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q seçenekler (düşük düzey Işlemler)](q-options-low-level-operations.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
