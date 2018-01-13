---
title: "-C (önişleme sırasında açıklamaları Koru) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.KeepComments
- /c
- VC.Project.VCCLWCECompilerTool.KeepComments
dev_langs: C++
helpviewer_keywords:
- comments, not stripping during preprocessing
- preserve comments during preprocessing
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d27e6ed0f6a2ff6e6f63bc1b87522fb598953c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-preserve-comments-during-preprocessing"></a>/C (Önişleme Sırasında Açıklamaları Koru)
Ön işleme sırasında açıklamaları korur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/C  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu derleyici seçeneği gerektirir **/E**, **/P**, veya **/EP** seçeneği.  
  
 Aşağıdaki kod örneği, kaynak kod açıklaması görüntülenir.  
  
```  
// C_compiler_option.cpp  
// compile with: /E /C /c  
int i;   // a variable  
```  
  
 Bu örnek şu çıkışı üretir.  
  
```  
#line 1 "C_compiler_option.cpp"  
int i;   // a variable  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **önişlemci** özellik sayfası.  
  
4.  Değiştirme **tutmak açıklamaları** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [/E (Stdout'a Önişle)](../../build/reference/e-preprocess-to-stdout.md)   
 [/P (dosyaya önişle)](../../build/reference/p-preprocess-to-a-file.md)   
 [/EP (#line yönergeleri olmadan stdout'ta Önişle)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)