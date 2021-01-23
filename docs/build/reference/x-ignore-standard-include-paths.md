---
description: 'Hakkında daha fazla bilgi edinin: `/X` (Standart içerme yollarını yoksay)'
title: /X (Standart yol eklemeyi yoksay)
ms.date: 01/21/2021
f1_keywords:
- /x
- VC.Project.VCCLCompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLWCECompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLCompilerTool.IgnoreStandardIncludePath
helpviewer_keywords:
- /X compiler option [C++]
- include files, ignore standard path
- -X compiler option [C++]
- include directories, ignore standard
- X compiler option
- Ignore Standard Include Paths compiler option
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
ms.openlocfilehash: 97d19027c41df7db9103c1c21d2f2d7b8d398e7e
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712810"
---
# <a name="x-ignore-standard-include-paths"></a>`/X` (Standart içerme yollarını yoksay)

Derleyicinin `PATH` ve ortam değişkenlerinde belirtilen dizinlerdeki içerme dosyalarını aramasını engeller `INCLUDE` .

## <a name="syntax"></a>Syntax

> **`/X`**

## <a name="remarks"></a>Açıklamalar

Bu seçeneği, standart ekleme dosyaları için alternatif bir yol belirtmek üzere [ `/I` (ek ekleme dizinleri)](i-additional-include-directories.md) seçeneğiyle kullanabilirsiniz.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **Önişlemci** özellik sayfasını seçin.

1. **Ignore standart Içerme yolunu** Değiştir özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komutta, **`/X`** derleyiciye ve ortam değişkenleri tarafından belirtilen konumları yok `PATH` `INCLUDE` **`/I`** saymasını söyler ve içerme dosyaları için aranacak dizini belirtir:

```cmd
CL /X /I \ALT\INCLUDE MAIN.C
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyicisi seçenekleri](compiler-options.md)<br/>
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)
