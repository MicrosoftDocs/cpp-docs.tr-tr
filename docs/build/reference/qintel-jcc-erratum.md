---
title: /QIntel-jcc-erratum
description: Microsoft C/C++ derleyicisi (MSVC)/Qıntel-JCC-eroytum seçeneğini açıklar.
ms.date: 01/07/2020
f1_keywords:
- QIntel-jcc-erratum
helpviewer_keywords:
- /QIntel-jcc-erratum
- -QIntel-jcc-erratum
ms.openlocfilehash: c66dd4bb25647ce193bce4db5dc4ebb1268277c0
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921379"
---
# <a name="qintel-jcc-erratum"></a>/QIntel-jcc-erratum

::: moniker range="<=msvc-150"

**/Qıntel-JCC-errampaseçeneği** , Visual Studio 2019 sürüm 16,5 ve sonraki sürümlerinde kullanılabilir.

::: moniker-end

::: moniker range=">=msvc-160"

Derleyicinin, bazı Intel işlemcilerinde Intel atsal kod (JCC) ermıtum mikro kod güncelleştirmesinden kaynaklanan performans etkisini hafifletmek için yönergeler ürettiğine ilişkin yönergeler üretir.

## <a name="syntax"></a>Syntax

> **/QIntel-jcc-erratum**

## <a name="remarks"></a>Açıklamalar

**/Qıntel-JCC-erktum** altında, derleyici, 32 baytlık bir sınırı çapraz veya sona ereden, atlamanın ve makro-kullanılmayan geçiş talimatlarını algılar. Bu yönergeleri sınıra göre hizalar. Bu değişiklik, bazı Intel işlemcilerde JCC ersumu önleyen mikro kod güncelleştirmelerinin performans etkisini azaltır. Errat hakkında daha fazla bilgi için bkz. Intel Web sitesinde [atlayan koşullu kod Için Azaltıcı Etkenler](https://www.intel.com/content/dam/support/us/en/documents/processors/mitigations-jump-conditional-code-erratum.pdf) .

**/Qıntel-JCC-errampaseçeneği** , Visual Studio 2019 sürüm 16,5 ve sonraki sürümlerinde kullanılabilir. Bu seçenek yalnızca x86 ve x64 ile hedeflenen derleyicilerde kullanılabilir. Seçeneği, ARM işlemcilerini hedefleyen derleyicilerde kullanılamaz.

**/Qıntel-JCC-erkıtum** seçeneği varsayılan olarak kapalıdır ve yalnızca iyileştirilmiş derlemelerde çalışmaktadır. Bu seçenek, kod boyutunu artırabilir.

**/Qıntel-JCC-errat** [/clr](clr-common-language-runtime-compilation.md)ile uyumsuzdur.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **C/C++** > **kod oluşturma** özellik sayfasını seçin.

1. **Intel JCC Errampaazaltma özelliğini etkinleştir** özelliğinin değerini seçin. Değişikliği uygulamak için **Tamam ' ı** seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q seçenekler (düşük düzey işlemler)](q-options-low-level-operations.md)\
[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)

::: moniker-end
