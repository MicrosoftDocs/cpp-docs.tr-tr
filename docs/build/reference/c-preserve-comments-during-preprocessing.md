---
title: /C (Önişleme Sırasında Açıklamaları Koru)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.KeepComments
- VC.Project.VCCLWCECompilerTool.KeepComments
helpviewer_keywords:
- comments, not stripping during preprocessing
- preserve comments during preprocessing
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
ms.openlocfilehash: f80ebf45dd396a3f92d9b755c56522d4731bb2d0
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440281"
---
# <a name="c-preserve-comments-during-preprocessing"></a>/C (Önişleme Sırasında Açıklamaları Koru)

Ön işleme sırasında açıklamaları korur.

## <a name="syntax"></a>Sözdizimi

```
/C
```

## <a name="remarks"></a>Açıklamalar

Bu derleyici seçeneği, **/e**, **/P**veya **/EP** seçeneğini gerektirir.

Aşağıdaki kod örneğinde kaynak kodu açıklaması görüntülenir.

```cpp
// C_compiler_option.cpp
// compile with: /E /C /c
int i;   // a variable
```

Bu örnek aşağıdaki çıktıyı oluşturacaktır.

```
#line 1 "C_compiler_option.cpp"
int i;   // a variable
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++**  klasörüne tıklayın.

1. **Önişlemci** Özellik sayfasına tıklayın.

1. **Yorumları tut** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[/E (stdout'a Önişle)](e-preprocess-to-stdout.md)<br/>
[/P (Dosyaya Önişle)](p-preprocess-to-a-file.md)<br/>
[/EP (#line Yönergeleri Olmadan stdout'ta Önişle)](ep-preprocess-to-stdout-without-hash-line-directives.md)
