---
title: "-Showıncludes (liste dosyaları içerir) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ShowIncludes
- VC.Project.VCCLCompilerTool.ShowIncludes
- /showincludes
dev_langs: C++
helpviewer_keywords:
- include files
- /showIncludes compiler option [C++]
- include files, displaying in compilation
- -showIncludes compiler option [C++]
- showIncludes compiler option [C++]
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 72f80202d2d1c8018e9c145951664d335ac759b7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="showincludes-list-include-files"></a>/showIncludes (Liste Dosyaları İçerir)
Dosyaları Ekle listesini çıkarmak derleyici neden olur. İç içe geçmiş içeren dosyalardır de (eklediğiniz dosyalarından dahil edilen görüntülenen dosyalar).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/showIncludes  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir içerme dosyası derleme sırasında karşılaşıldığında, bir ileti çıktı, örneğin şöyledir:  
  
```  
Note: including file: d:\MyDir\include\stdio.h  
```  
  
 İç içe geçmiş dahil dosyaları belirtilir girinti, her iç içe geçme düzeyi için bir boşluk tarafından örneğin:  
  
```  
Note: including file: d:\temp\1.h  
Note: including file:  d:\temp\2.h  
```  
  
 Bu durumda, `2.h` gelen içinde dahil edildiğinden `1.h`, bu nedenle girinti.  
  
 **/Showıncludes** seçeneği yayar için `stderr`değil `stdout`.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **Gelişmiş** özellik sayfası.  
  
4.  Değiştirme **Göster içeren** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)