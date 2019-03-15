---
title: /FI (Zorla Dahil Edilen Dosyayı Adlandır)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.ForcedIncludes
- VC.Project.VCCLCompilerTool.ForcedIncludeFiles
- VC.Project.VCCLWCECompilerTool.ForcedIncludeFiles
- /fi
helpviewer_keywords:
- FI compiler option [C++]
- -FI compiler option [C++]
- /FI compiler option [C++]
- preprocess header file compiler option [C++]
ms.assetid: 07e79577-8152-4df9-a64c-aae08c603397
ms.openlocfilehash: 2e85706a0266696b83fe1a1a6cdc45ba3399fc21
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809229"
---
# <a name="fi-name-forced-include-file"></a>/FI (Zorla Dahil Edilen Dosyayı Adlandır)

Önişlemci belirtilen üstbilgi dosyasını işlemek neden olur.

## <a name="syntax"></a>Sözdizimi

```
/FI[ ]pathname
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek dosyayı çift tırnak işaretleri ile belirtmekle aynı etkiye sahip bir `#include` komut satırında, CL ortam değişkeninde veya komut dosyası içinde belirtilen her kaynak dosyasının ilk satırındaki yönergesi. Birden çok kullanırsanız **/FI** seçenekleri, dosyaları, CL ile bunların işlenme sırasını bulunmaktadır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **zorla içerir** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı Dosyası (/F) Seçenekleri](output-file-f-options.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
[Yol Adını Belirtme](specifying-the-pathname.md)
