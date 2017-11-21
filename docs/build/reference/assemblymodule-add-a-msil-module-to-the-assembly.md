---
title: "-ASSEMBLYMODULE (derlemeye MSIL Modülü Ekle) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /assemblymodule
- VC.Project.VCLinkerTool.AddModuleNamesToAssembly
dev_langs: C++
helpviewer_keywords:
- ASSEMBLYMODULE linker option
- assemblies [C++], adding modules to
- assemblies [C++]
- /ASSEMBLYMODULE linker option
- -ASSEMBLYMODULE linker option
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9709a98ee6528a2081f98351126cc84529b0733b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="assemblymodule-add-a-msil-module-to-the-assembly"></a>/ASSEMBLYMODULE (Derlemeye MSIL Modülü Ekle)
```  
/ASSEMBLYMODULE:filename  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *Dosya adı*  
 Bu derlemede dahil etmek istediğiniz modül.  
  
## <a name="remarks"></a>Açıklamalar  
 /ASSEMBLYMODULE seçeneği, bir derleme bir modül başvurusu eklemenizi sağlar. Modül türü bilgileri modül başvurusu eklenen derleme program kullanılamaz. Ancak, modül türü bilgileri bütünleştirilmiş koduna başvuruyor herhangi bir program için kullanılabilir.  
  
 Kullanım [#using](../../preprocessor/hash-using-directive-cpp.md) hem bir derlemeyi modülü başvuru ekleyin ve modülün türü bilgileri derleme program kullanımına.  
  
 Örneğin, aşağıdaki senaryoları düşünün:  
  
1.  Sahip bir modül oluşturma [/LN](../../build/reference/ln-create-msil-module.md).  
  
2.  /ASSEMBLYMODULE farklı bir proje ile bir derlemeyi oluşturacak geçerli derlemede modül eklemek için kullanın. Bu proje modülüyle başvuruda bulunmaz `#using`.  
  
3.  Bu bütünleştirilmiş koduna başvuruyor herhangi bir projeye şimdi modülden türlerini de kullanabilirsiniz.  
  
 Derleme oluşturma etkileyen diğer bağlayıcı seçenekleri şunlardır:  
  
-   [/ ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/ DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/ NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
-   [/ KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/ KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 Visual C++ bağlayıcı .netmodule dosyaları giriş olarak kabul eder ve bağlayıcı tarafından üretilen çıkış dosyası bir derlemeyi ya da hiç çalışma zamanı bağımlılığı herhangi bir bağlayıcıya giriş .netmodules ile .netmodule olacaktır.  Daha fazla bilgi için bkz: [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **giriş** özellik sayfası.  
  
4.  Değiştirme **derleme Modül Ekle** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)