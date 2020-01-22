---
title: /Qıntel-JCC-errat
description: Microsoft C/C++ DERLEYICISI (MSVC)/Qıntel-JCC-errat seçeneğini açıklar.
ms.date: 01/07/2020
f1_keywords:
- QIntel-jcc-erratum
helpviewer_keywords:
- /QIntel-jcc-erratum
- -QIntel-jcc-erratum
ms.openlocfilehash: f311da04b833b06124c5e6237ea83a31319858ca
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76520881"
---
# <a name="qintel-jcc-erratum"></a>/Qıntel-JCC-errat

::: moniker range="<=vs-2017"

**/Qıntel-JCC-errampaseçeneği** , Visual Studio 2019 sürüm 16,5 ve sonraki sürümlerinde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2019"

Derleyicinin, bazı Intel işlemcilerinde Intel atsal kod (JCC) ermıtum mikro kod güncelleştirmesinden kaynaklanan performans etkisini hafifletmek için yönergeler ürettiğine ilişkin yönergeler üretir.

## <a name="syntax"></a>Sözdizimi

> **/Qıntel-JCC-errat**

## <a name="remarks"></a>Açıklamalar

**/Qıntel-JCC-erktum**altında, derleyici, 32 baytlık bir sınırı çapraz veya sona ereden, atlamanın ve makro-kullanılmayan geçiş talimatlarını algılar. Bu yönergeleri sınıra göre hizalar. Bu değişiklik, bazı Intel işlemcilerde JCC ersumu önleyen mikro kod güncelleştirmelerinin performans etkisini azaltır. Errat hakkında daha fazla bilgi için bkz. Intel Web sitesinde [atlayan koşullu kod Için Azaltıcı Etkenler](https://www.intel.com/content/dam/support/us/en/documents/processors/mitigations-jump-conditional-code-erratum.pdf) .

**/Qıntel-JCC-errampaseçeneği** , Visual Studio 2019 sürüm 16,5 ve sonraki sürümlerinde kullanılabilir. Bu seçenek yalnızca x86 ve x64 ile hedeflenen derleyicilerde kullanılabilir. Seçeneği, ARM işlemcilerini hedefleyen derleyicilerde kullanılamaz.

**/Qıntel-JCC-erkıtum** seçeneği varsayılan olarak kapalıdır ve yalnızca iyileştirilmiş derlemelerde çalışmaktadır. Bu seçenek, kod boyutunu artırabilir.

**/Qıntel-JCC-errat** [/clr](clr-common-language-runtime-compilation.md)ile uyumsuzdur.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **CC++ /** > **kod oluşturma** Özellik sayfası ' nı seçin.

1. **Intel JCC Errampaazaltma özelliğini etkinleştir** özelliğinin değerini seçin. Değişikliği uygulamak için **Tamam ' ı** seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q seçenekler (düşük düzey işlemler)](q-options-low-level-operations.md)\
[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)

::: moniker-end
