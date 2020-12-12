---
description: Şu konuda daha fazla bilgi edinin:/FX (eklenen kodu Birleştir)
title: /Fx (Eklenen Kodu Birleştir)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ExpandAttributedSource
- /Fx
- VC.Project.VCCLCompilerTool.ExpandAttributedSource
helpviewer_keywords:
- Fx compiler option [C++]
- -Fx compiler option [C++]
- injected code
- merging injected code
- /Fx compiler option [C++]
ms.assetid: 14f0e301-3bab-45a3-bbdf-e7ce66f20560
ms.openlocfilehash: 0c0aeea4c3a72f37848615d80c5ee6a5a807d838
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200357"
---
# <a name="fx-merge-injected-code"></a>/Fx (Eklenen Kodu Birleştir)

Kaynak ile birleştirilen eklenen kodla her kaynak dosyanın bir kopyasını oluşturur.

## <a name="syntax"></a>Syntax

```
/Fx
```

## <a name="remarks"></a>Açıklamalar

Bir birleştirilmiş kaynak dosyayı orijinal bir kaynak dosyasından ayırt etmek için, **/FX** dosya adı ve dosya uzantısı arasına bir. mrg uzantısı ekler. Örneğin, öznitelikli kodu içeren ve **/FX** Ile oluşturulan MyCode. cpp adlı bir dosya, aşağıdaki kodu Içeren MyCode. MRG. cpp adlı bir dosya oluşturur:

```
//+++ Start Injected Code
[no_injected_text(true)];      // Suppress injected text, it has
                               // already been injected
#pragma warning(disable: 4543) // Suppress warnings about skipping
                               // injected text
#pragma warning(disable: 4199) // Suppress warnings from attribute
                               // providers
//--- End Injected Code
```

Bir. mrg dosyasında, bir öznitelik nedeniyle eklenen kod aşağıdaki gibi sınırlandırılır:

```
//+++ Start Injected Code
...
//--- End Injected Code
```

[No_injected_text](../../windows/attributes/no-injected-text.md) özniteliği, metin olmadan. mrg dosyasının derlenmesi için izin veren bir. mrg dosyasına katıştırılır.

. MRG kaynak dosyasının, derleyici tarafından eklenen kaynak kodun temsili olduğunu bilmeniz gerekir. . MRG dosyası tam olarak özgün kaynak dosya olarak derlenmeyebilir veya çalışmayabilir.

Makrolar. mrg dosyasında genişletilmez.

Programınız eklenen kodu kullanan bir üstbilgi dosyası içeriyorsa, **/FX** bu üst bilgi için bir. MRG. h dosyası oluşturur. **/FX** , eklenen kodu kullanmayan içerme dosyalarını birleştirmiyor.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Çıkış dosyaları** Özellik sayfasına tıklayın.

1. Özelliği **belirtilmiş kaynağı Genişlet** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExpandAttributedSource%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı dosyası (/F) seçenekleri](output-file-f-options.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
