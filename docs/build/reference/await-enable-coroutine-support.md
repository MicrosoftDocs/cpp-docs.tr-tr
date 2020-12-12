---
description: Daha fazla bilgi edinin:/await (eş yordam olamaz desteğini etkinleştir)
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
ms.openlocfilehash: a36c2233085a1c38ed61aed7d6ea757762179cc4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182768"
---
# <a name="await-enable-coroutine-support"></a>/await (Eş yordam desteğini etkinleştir)

Eş yordamları için derleyici desteğini etkinleştirmek üzere **/await** derleyici seçeneğini kullanın.

## <a name="syntax"></a>Syntax

> /await

## <a name="remarks"></a>Açıklamalar

**/Await** derleyici seçeneği, C++ eş değerleri ve, ve anahtar kelimeleri için derleyici desteği **`co_await`** sunar **`co_yield`** **`co_return`** . Bu seçenek varsayılan olarak kapalıdır. Visual Studio 'da eş yordamlar için destek hakkında bilgi için bkz. [Visual Studio Ekip Blogu](https://devblogs.microsoft.com/cppblog/category/coroutine/). Eş standart teklif hakkında daha fazla bilgi için bkz. [N4628 çalışma taslağı, eş yordamın C++ uzantıları Için Teknik belirtim](https://wg21.link/n4628).

**/Await** seçeneği Visual Studio 2015 ' den başlayarak kullanılabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenizin **Özellik sayfaları** iletişim kutusunu açın.

1. **Yapılandırma özellikleri** altında **C/C++** klasörünü genişletin ve **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusuna **/await** derleyici seçeneğini girin. Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
