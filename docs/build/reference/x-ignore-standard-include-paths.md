---
title: -X (standart yoksayma yolu dahil) | Microsoft Docs
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
ms.openlocfilehash: c5d246c43a1f234426b33ac640b3e1bb706d2f72
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="x-ignore-standard-include-paths"></a>/X (Standart Yol Eklemeyi Yoksay)
Belirtilen yol ve INCLUDE ortam değişkenleri dizinlerdeki içerme dosyaları için arama derleyici engeller.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/X  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek ile kullanabileceğiniz [/ı (ek içeren dizinler)](../../build/reference/i-additional-include-directories.md) (**/I**`directory`) seçeneği.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **önişlemci** özellik sayfası.  
  
4.  Değiştirme **standart dahil yol Yoksay** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komutta `/X` yolu ve INCLUDE ortam değişkenleri tarafından belirtilen konumları yoksay bildirir ve `/I` aranacak dizine belirtir dosyaları içerir:  
  
```  
CL /X /I \ALT\INCLUDE MAIN.C  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)