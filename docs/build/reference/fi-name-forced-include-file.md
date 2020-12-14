---
description: Daha fazla bilgi edinin:/FI (zorunlu Içerme dosyasını Adlandır)
title: /FI (Zorla Dahil Edilen Dosyayı Adlandır)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.ForcedIncludes
- VC.Project.VCCLCompilerTool.ForcedIncludeFiles
- VC.Project.VCCLWCECompilerTool.ForcedIncludeFiles
helpviewer_keywords:
- FI compiler option [C++]
- -FI compiler option [C++]
- /FI compiler option [C++]
- preprocess header file compiler option [C++]
ms.assetid: 07e79577-8152-4df9-a64c-aae08c603397
ms.openlocfilehash: 614a06511df1b407adc39bb8ec567a9674ffb3cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200656"
---
# <a name="fi-name-forced-include-file"></a>/FI (Zorla Dahil Edilen Dosyayı Adlandır)

Önişlemci 'nin belirtilen üst bilgi dosyasını işlemesini sağlar.

## <a name="syntax"></a>Syntax

```
/FI[ ]pathname
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, `#include` komut satırında, CL ortam değişkeninde veya bir komut dosyasında belirtilen her kaynak dosyanın ilk satırındaki bir yönergede çift tırnak işaretleriyle birlikte dosyayı belirtmekle aynı etkiye sahiptir. Birden çok **/FI** seçeneği kullanırsanız, dosyalar CL tarafından işlendikleri sıraya dahil edilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Gelişmiş** Özellik sayfasına tıklayın.

1. **Zorunlu Içerme dosyası** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı dosyası (/F) seçenekleri](output-file-f-options.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[Yol adını belirtme](specifying-the-pathname.md)
