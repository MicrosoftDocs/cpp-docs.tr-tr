---
title: -AI (meta veri dizinlerini belirt) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.AdditionalUsingDirectories
- VC.Project.VCNMakeTool.AssemblySearchPath
- /AI
- VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories
dev_langs:
- C++
helpviewer_keywords:
- /AI compiler option [C++]
- AI compiler option [C++]
- -AI compiler option [C++]
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bde5c93c8a211bb0fc66028932a0a7d50415236d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369438"
---
# <a name="ai-specify-metadata-directories"></a>/AI (Meta Veri Dizinlerini Belirt)
Derleyici dosya referansları geçirilen çözümlemek için arayacağı bir dizini belirtir `#using` yönergesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/AIdirectory  
```  
  
## <a name="arguments"></a>Arguments  
 `directory`  
 Derleyicinin arama yapacağı dizin veya yol.  
  
## <a name="remarks"></a>Açıklamalar  
 Yalnızca bir dizin için geçirilebilir bir **/AI** çağırma. Bir tane belirtin **/AI** derleyici arama yapmak istediğiniz her bir yol için seçeneği. Örneğin, C:\Project\Meta ve C:\Common\Meta derleyici arama yolu eklemek için `#using` yönergeleri, ekleyin `/AI"C:\Project\Meta" /AI"C:\Common\Meta"` derleyici komut satırı için veya her dizinine ekleme **ek # dizin using** Visual Studio özelliği.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Gezinti bölmesinde seçin **yapılandırma özellikleri**, **C/C++**, **genel**.  
  
3.  Değiştirme **ek # dizin using** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [#using yönergesi](../../preprocessor/hash-using-directive-cpp.md)