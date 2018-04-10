---
title: -I (ek içeren dizinler) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories
- VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories
- /I
- VC.Project.VCNMakeTool.IncludeSearchPath
dev_langs:
- C++
helpviewer_keywords:
- /I compiler option [C++]
- Additional Include Directories compiler option
- I compiler option [C++]
- -I compiler option [C++]
- set include directories
- include directories, compiler option [C++]
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bfbf962a92af22d3e724c592fec6cf812b610dc7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="i-additional-include-directories"></a>/I (Ek İçeren Dizinler)
Bir dizin için dosyaları Ekle aranır dizinlerin listesi ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/I[ ]directory  
```  
  
## <a name="arguments"></a>Arguments  
 `directory`  
 Dizinleri listesine eklemek için dizin için dosyaları Ekle aranır.  
  
## <a name="remarks"></a>Açıklamalar  
 Birden fazla dizin eklemek için bu seçeneği birden çok kez kullanın. Yalnızca belirtilen içerme dosyası bulunana kadar dizinler aranır.  
  
 Yoksay standart yol eklemeyi ile bu seçeneği kullanabilirsiniz ([/X (Yoksay standart yol eklemeyi)](../../build/reference/x-ignore-standard-include-paths.md)) seçeneği.  
  
 Derleyici dizinleri aşağıdaki sırayla arar:  
  
1.  Kaynak dosyasını içeren dizinler.  
  
2.  İle belirtilen dizinleri **/I** CL bunları karşılaştığı sırada seçeneği.  
  
3.  Belirtilen dizin **INCLUDE** ortam değişkeni.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **genel** özellik sayfası.  
  
4.  Değiştirme **ek içeren dizinler** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komutu aşağıdaki sırayla MAIN.c tarafından istenen içerme dosyaları arar: ilk MAIN.c, ardından \INCLUDE dizin ardından \MY\INCLUDE dizininde içeren ve son olarak dizinler atanmış INCLUDE dizininde ortam değişkeni.  
  
```  
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)