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
ms.openlocfilehash: eeab3f4a1afc73e341f04222a55c8ce429490742
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078442"
---
# <a name="await-enable-coroutine-support"></a>/await (Eş yordam desteğini etkinleştir)

Eş yordamları için derleyici desteğini etkinleştirmek üzere **/await** derleyici seçeneğini kullanın.

## <a name="syntax"></a>Sözdizimi

> /await

## <a name="remarks"></a>Açıklamalar

**/Await** derleyici seçeneği, eş değerleri ve C++ **co_await**, **co_yield**ve **co_return**anahtar kelimeleri için derleyici desteği sunar. Bu seçenek varsayılan olarak kapalıdır. Visual Studio 'da eş yordamlar için destek hakkında bilgi için bkz. [Visual Studio Ekip Blogu](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/). Eş standart teklif hakkında daha fazla bilgi için bkz. [N4628 çalışma taslağı, eş için Uzantılar Için C++ teknik belirtim](https://wg21.link/n4628).

**/Await** seçeneği Visual Studio 2015 ' den başlayarak kullanılabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenizin **Özellik sayfaları** iletişim kutusunu açın.

1. **Yapılandırma özellikleri**altında **CC++ /** klasörünü genişletin ve **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusuna **/await** derleyici seçeneğini girin. Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
