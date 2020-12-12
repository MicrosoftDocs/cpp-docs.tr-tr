---
description: Daha fazla bilgi edinin:/C (ön Işleme sırasında açıklamaları koru)
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
ms.openlocfilehash: 2cf5bf562db78dcb6c570d7313b56ad4a9fc5adb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179362"
---
# <a name="c-preserve-comments-during-preprocessing"></a>/C (Önişleme Sırasında Açıklamaları Koru)

Ön işleme sırasında açıklamaları korur.

## <a name="syntax"></a>Syntax

```
/C
```

## <a name="remarks"></a>Açıklamalar

Bu derleyici seçeneği, **/e**, **/P** veya **/EP** seçeneğini gerektirir.

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

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Önişlemci** Özellik sayfasına tıklayın.

1. **Yorumları tut** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[/E (stdout'a Önişle)](e-preprocess-to-stdout.md)<br/>
[/P (bir dosyaya ön Işlem)](p-preprocess-to-a-file.md)<br/>
[/EP (#line yönergeleri olmadan stdout için önceden Işleme)](ep-preprocess-to-stdout-without-hash-line-directives.md)
