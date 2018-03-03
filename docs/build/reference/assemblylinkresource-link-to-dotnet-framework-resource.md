---
title: "-ASSEMBLYLINKRESOURCE (.NET Framework kaynağına bağlantı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ASSEMBLYLINKRESOURCE
- VC.Project.VCLinkerTool.AssemblyLinkResource
dev_langs:
- C++
helpviewer_keywords:
- -ASSEMBLYLINKRESOURCE linker option
- ASSEMBLYLINKRESOURCE linker option
- /ASSEMBLYLINKRESOURCE linker option
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6a5ab1211cf3a1d5c834c0d32f1840db1bc2bf1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="assemblylinkresource-link-to-net-framework-resource"></a>/ASSEMBLYLINKRESOURCE (.NET Framework Kaynağına Bağlantı)
```  
/ASSEMBLYLINKRESOURCE:filename  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *Dosya adı*  
 Derlemeden bağlamak istediğiniz .NET Framework kaynak dosyası.  
  
## <a name="remarks"></a>Açıklamalar  
 /ASSEMBLYLINKRESOURCE seçeneği bir .NET Framework kaynağına bağlantı çıktı dosyasında oluşturur; Kaynak dosyanın çıkış dosyasında yerleştirilmedi. [/ ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) kaynak dosyasını çıktı dosyasına katıştırır.  
  
 Bağlı kaynaklar ile bağlayıcı oluşturduğunuzda derlemesindeki ortak.  
  
 / ASSEMBLYLINKRESOURCE gerektirir derleme içerdiğini [/CLR](../../build/reference/clr-common-language-runtime-compilation.md); [/LN](../../build/reference/ln-create-msil-module.md) veya [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) ile /ASSEMBLYLINKRESOURCE izin verilmiyor.  
  
 Varsa *filename* , örneğin, tarafından oluşturulan bir .NET Framework kaynak dosyası [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) veya geliştirme ortamında üyelerle erişilebileceğini **System.Resources** ad alanı. Daha fazla bilgi için bkz: [System.Resources.ResourceManager](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx). Diğer tüm kaynaklar için kullanmak **GetManifestResource** \* yöntemleri **System.Reflection.Assembly** çalışma zamanında kaynağa erişmek için sınıf.  
  
 *filename* herhangi bir dosya biçiminde olabilir. Örneğin, genel derleme önbelleğine yüklü ve yönetilen kod derlemesindeki erişilen derleme yerel bir DLL parçası olmak isteyebilirsiniz.  
  
 Derleme oluşturma etkileyen diğer bağlayıcı seçenekleri şunlardır:  
  
-   [/ ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/ DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/ KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [/ KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/ NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Seçenek içine türünü **ek seçenekler** kutusu.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)