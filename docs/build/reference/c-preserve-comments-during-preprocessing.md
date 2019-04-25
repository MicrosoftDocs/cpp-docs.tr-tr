---
title: /C (Önişleme Sırasında Açıklamaları Koru)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.KeepComments
- /c
- VC.Project.VCCLWCECompilerTool.KeepComments
helpviewer_keywords:
- comments, not stripping during preprocessing
- preserve comments during preprocessing
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
ms.openlocfilehash: c5854fd1255ab509d8778828de25638dd821d74b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272838"
---
# <a name="c-preserve-comments-during-preprocessing"></a>/C (Önişleme Sırasında Açıklamaları Koru)

Ön işlem sırasında yorumları korur.

## <a name="syntax"></a>Sözdizimi

```
/C
```

## <a name="remarks"></a>Açıklamalar

Bu derleyici seçeneğini gerektirir **/E**, **/P**, veya **/EP** seçeneği.

Aşağıdaki kod örneği, kaynak kod açıklaması gösterilir.

```
// C_compiler_option.cpp
// compile with: /E /C /c
int i;   // a variable
```

Bu örnek aşağıdaki çıktıyı oluşturur.

```
#line 1 "C_compiler_option.cpp"
int i;   // a variable
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **önişlemci** özellik sayfası.

1. Değiştirme **açıklamaları tut** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[/E (stdout'a Önişle)](e-preprocess-to-stdout.md)<br/>
[/P (Dosyaya Önişle)](p-preprocess-to-a-file.md)<br/>
[/EP (#line Yönergeleri Olmadan stdout'ta Önişle)](ep-preprocess-to-stdout-without-hash-line-directives.md)
