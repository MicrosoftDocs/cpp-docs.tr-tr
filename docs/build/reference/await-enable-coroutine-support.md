---
title: -await (eş yordam desteğini etkinleştir) | Microsoft Docs
ms.custom: ''
ms.date: 08/15/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /await
- -await
dev_langs:
- C++
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5da401f940a39c135ba0b64571b6330a42fed796
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725523"
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

2. Altında **yapılandırma özellikleri**, genişletme **C/C++** klasörü seçin **komut satırı** özellik sayfası.

3. Girin **/ await** derleyici seçeneğini **ek seçenekler** kutusu. Seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)