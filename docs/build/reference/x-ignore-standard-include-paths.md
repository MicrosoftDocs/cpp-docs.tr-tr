---
description: 'Hakkında daha fazla bilgi edinin: `/X` (Standart içerme yollarını yoksay)'
title: /X (Standart yol eklemeyi yoksay)
ms.date: 07/31/2020
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
ms.openlocfilehash: 69936b80893de2c45622ec9973a218a94e8029a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261014"
---
# <a name="x-ignore-standard-include-paths"></a>`/X` (Standart içerme yollarını yoksay)

Derleyicinin yolda belirtilen dizinlerdeki içerme dosyalarını aramasını ve ortam değişkenlerini IÇERMESINI önler.

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

Aşağıdaki komutta, **`/X`** DERLEYICININ yol tarafından belirtilen konumları yok saymasını ve ortam DEĞIŞKENLERINI içermesini ve **`/I`** içerme dosyaları için aranacak dizini belirteceklerini söyler:

```cmd
CL /X /I \ALT\INCLUDE MAIN.C
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyicisi seçenekleri](compiler-options.md)<br/>
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)
