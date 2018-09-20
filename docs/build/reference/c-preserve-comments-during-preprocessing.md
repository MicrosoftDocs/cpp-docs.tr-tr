---
title: -C (önişleme sırasında açıklamaları Koru) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.KeepComments
- /c
- VC.Project.VCCLWCECompilerTool.KeepComments
dev_langs:
- C++
helpviewer_keywords:
- comments, not stripping during preprocessing
- preserve comments during preprocessing
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8716c0a0f954b0a2ad0bbe0e25c29a4445b11823
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428349"
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

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **önişlemci** özellik sayfası.

1. Değiştirme **açıklamaları tut** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[/E (stdout'a Önişle)](../../build/reference/e-preprocess-to-stdout.md)<br/>
[/P (Dosyaya Önişle)](../../build/reference/p-preprocess-to-a-file.md)<br/>
[/EP (#line Yönergeleri Olmadan stdout'ta Önişle)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)