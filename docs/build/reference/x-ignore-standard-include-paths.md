---
title: -X (standart yoksayma yolu dahil) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /x
- VC.Project.VCCLCompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLWCECompilerTool.OVERWRITEStandardIncludePath
dev_langs: C++
helpviewer_keywords:
- /X compiler option [C++]
- include files, ignore standard path
- -X compiler option [C++]
- include directories, ignore standard
- X compiler option
- Ignore Standard Include Paths compiler option
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a15294e1a63b16124d8907639fbd2e6bb705f1aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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