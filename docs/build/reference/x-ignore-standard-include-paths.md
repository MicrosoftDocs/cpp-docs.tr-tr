---
title: -X (standart ekleme yolunu yoksay yolları dahil) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /x
- VC.Project.VCCLCompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLWCECompilerTool.OVERWRITEStandardIncludePath
dev_langs:
- C++
helpviewer_keywords:
- /X compiler option [C++]
- include files, ignore standard path
- -X compiler option [C++]
- include directories, ignore standard
- X compiler option
- Ignore Standard Include Paths compiler option
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 994568d74c63e612b55d1101ce957e646c555e4a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707440"
---
# <a name="x-ignore-standard-include-paths"></a>/X (Standart Yol Eklemeyi Yoksay)

Derleyici, PATH ve INCLUDE Ortam değişkenlerinde belirtilen dizinlerde ekleme dosyalarını aramasını engeller.

## <a name="syntax"></a>Sözdizimi

```
/X
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek ile kullanabileceğiniz [/ı (ek içeren dizinler)](../../build/reference/i-additional-include-directories.md) (**/I**`directory`) seçeneği.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **önişlemci** özellik sayfası.

1. Değiştirme **yoksay standart yolu Ekle** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komutta `/X` derleyiciye PATH ve INCLUDE ortam değişkenleri tarafından belirtilen konumları yoksay ve `/I` aranacak dizini belirtir dosyaları içerir:

```
CL /X /I \ALT\INCLUDE MAIN.C
```

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)