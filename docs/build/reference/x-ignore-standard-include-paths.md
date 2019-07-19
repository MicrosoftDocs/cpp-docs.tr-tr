---
title: /X (Standart Yol Eklemeyi Yoksay)
ms.date: 07/18/2019
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
ms.openlocfilehash: 16f903b98d69472fe1a33b084fe6393ecf9ec001
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341047"
---
# <a name="x-ignore-standard-include-paths"></a>/X (Standart Yol Eklemeyi Yoksay)

Derleyicinin yolda belirtilen dizinlerdeki içerme dosyalarını aramasını ve ortam değişkenlerini IÇERMESINI önler.

## <a name="syntax"></a>Sözdizimi

```
/X
```

## <a name="remarks"></a>Açıklamalar

Bu seçeneği [/ı (ek içerme dizinleri)](i-additional-include-directories.md) ( **/i**`directory`) seçeneğiyle kullanabilirsiniz.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++**  klasörüne tıklayın.

1. **Önişlemci** Özellik sayfasına tıklayın.

1. **Ignore standart Içerme yolunu** Değiştir özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komutta, `/X` derleyiciye yol tarafından belirtilen konumları yok saymasını ve ortam değişkenlerinin dahil edileceğini ve `/I` ekleme dosyalarının aranacağı dizini belirteceklerini söyler:

```
CL /X /I \ALT\INCLUDE MAIN.C
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
