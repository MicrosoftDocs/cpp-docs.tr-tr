---
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
ms.openlocfilehash: 6460f75e2cad81bc1dcc540e3c687de5d0dc0d32
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439794"
---
# <a name="fi-name-forced-include-file"></a>/FI (Zorla Dahil Edilen Dosyayı Adlandır)

Önişlemci 'nin belirtilen üst bilgi dosyasını işlemesini sağlar.

## <a name="syntax"></a>Sözdizimi

```
/FI[ ]pathname
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, komut satırında, CL ortam değişkeninde veya bir komut dosyasında belirtilen her kaynak dosyanın ilk satırında bir `#include` yönergesinde çift tırnak işaretleriyle birlikte dosyayı belirtirken de aynı etkiye sahiptir. Birden çok **/FI** seçeneği kullanırsanız, dosyalar CL tarafından işlendikleri sıraya dahil edilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++**  klasörüne tıklayın.

1. **Gelişmiş** Özellik sayfasına tıklayın.

1. **Zorunlu Içerme dosyası** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı Dosyası (/F) Seçenekleri](output-file-f-options.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[Yol Adını Belirtme](specifying-the-pathname.md)
