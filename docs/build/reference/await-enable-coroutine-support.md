---
title: /await (Eş yordam desteğini etkinleştir)
ms.date: 08/15/2017
f1_keywords:
- /await
- -await
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
ms.openlocfilehash: 526216ba2ae259b53bcf77691ebd09a6152b83f0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223934"
---
# <a name="await-enable-coroutine-support"></a>/await (Eş yordam desteğini etkinleştir)

Eş yordamları için derleyici desteğini etkinleştirmek üzere **/await** derleyici seçeneğini kullanın.

## <a name="syntax"></a>Sözdizimi

> /await

## <a name="remarks"></a>Açıklamalar

**/Await** derleyici seçeneği, C++ eş değerleri ve, ve anahtar kelimeleri için derleyici desteği **`co_await`** sunar **`co_yield`** **`co_return`** . Bu seçenek varsayılan olarak kapalıdır. Visual Studio 'da eş yordamlar için destek hakkında bilgi için bkz. [Visual Studio Ekip Blogu](https://devblogs.microsoft.com/cppblog/category/coroutine/). Eş standart teklif hakkında daha fazla bilgi için bkz. [N4628 çalışma taslağı, eş yordamın C++ uzantıları Için Teknik belirtim](https://wg21.link/n4628).

**/Await** seçeneği Visual Studio 2015 ' den başlayarak kullanılabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenizin **Özellik sayfaları** iletişim kutusunu açın.

1. **Yapılandırma özellikleri**altında **C/C++** klasörünü genişletin ve **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusuna **/await** derleyici seçeneğini girin. Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
