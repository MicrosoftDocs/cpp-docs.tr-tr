---
title: / await (eş yordam desteğini etkinleştir)
ms.date: 08/15/2017
f1_keywords:
- /await
- -await
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
ms.openlocfilehash: c0c8c0183c356900ba8f95d39e427d56eb1ec96b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809528"
---
# <a name="await-enable-coroutine-support"></a>/ await (eş yordam desteğini etkinleştir)

Kullanım **/ await** eş yordamlar için derleyici desteği etkinleştirme derleyici seçeneği.

## <a name="syntax"></a>Sözdizimi

> / await

## <a name="remarks"></a>Açıklamalar

**/ Await** derleyici seçeneği anahtar sözcükleri ve C++ eş yordamlar için derleyici desteği sağlayan **co_await**, **co_yield**, ve **co_return**. Varsayılan olarak bu seçenek kapalıdır. Eş yordamlar Visual Studio desteği hakkında daha fazla bilgi için bkz: [Visual Studio Ekip blog'u](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/). Eş yordamlar standart teklifi hakkında daha fazla bilgi için bkz. [N4628 çalışma Taslak, eş yordamlar için C++ uzantıları teknik belirtim](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/n4628.pdf).

**/ Await** seçeneği olan Visual Studio 2015'te sonraki sürümlerinde kullanılabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenizin açın **özellik sayfaları** iletişim kutusu.

1. Altında **yapılandırma özellikleri**, genişletme **C/C++** klasörü seçin **komut satırı** özellik sayfası.

1. Girin **/ await** derleyici seçeneğini **ek seçenekler** kutusu. Seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
