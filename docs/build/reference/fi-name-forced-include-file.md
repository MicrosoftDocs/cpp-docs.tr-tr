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
ms.openlocfilehash: b65fe37306e8b2469a32007bdd2c2564e334bc97
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481256"
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

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **zorla içerir** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Çıktı Dosyası (/F) Seçenekleri](../../build/reference/output-file-f-options.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Yol Adını Belirtme](../../build/reference/specifying-the-pathname.md)