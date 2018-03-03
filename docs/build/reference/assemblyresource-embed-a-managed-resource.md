---
title: "-ASSEMBLYRESOURCE (yönetilen kaynağı katıştır) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.EmbedManagedResourceFile
- /ASSEMBLYRESOURCE
dev_langs:
- C++
helpviewer_keywords:
- ASSEMBLYRESOURCE linker option
- assemblies [C++]
- -ASSEMBLYRESOURCE linker option
- assemblies [C++], linking resource files
- /ASSEMBLYRESOURCE linker option
ms.assetid: 0ce6e1fb-921b-4b1b-a59c-d35388d789f2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed8fd2b127a828eb8279671817cc4f099ae528c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="assemblyresource-embed-a-managed-resource"></a>/ASSEMBLYRESOURCE (Yönetilen Kaynağı Katıştır)
```  
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]  
```  
  
## <a name="parameters"></a>Parametreler  
 *Dosya adı*  
 Bu derlemede katıştırmak istediğiniz yönetilen kaynak.  
  
 *adı*  
 İsteğe bağlı. Kaynak için mantıksal ad; kaynağı yüklemek için kullanılan ad. Varsayılan dosya adıdır.  
  
 İsteğe bağlı olarak, dosya derleme bildiriminde özel olup olmayacağını belirtebilirsiniz. Varsayılan olarak, *adı* bütünleştirilmiş kodunda geneldir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir kaynak derlemede katıştırmak için /ASSEMBLYRESOURCE seçeneğini kullanın.  
  
 Bağlayıcı ile oluşturduğunuzda derlemesindeki ortak kaynaklardır. Bağlayıcı derlemedeki kaynağın yeniden adlandırmak izin vermiyor.  
  
 Varsa *filename* , örneğin, tarafından oluşturulan bir .NET Framework kaynak (.resources) dosyası [kaynak dosya oluşturucu (Resgen.exe)](/dotnet/framework/tools/resgen-exe-resource-file-generator) veya geliştirme ortamında, bu üyelerle erişilebilir **System.Resources** ad alanı (bkz [System.Resources.ResourceManager](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx) daha fazla bilgi için). Diğer tüm kaynaklar için kullanmak **GetManifestResource** \* yöntemleri **System.Reflection.Assembly** çalışma zamanında kaynağa erişmek için sınıf.  
  
 Derleme oluşturma etkileyen diğer bağlayıcı seçenekleri şunlardır:  
  
-   [/ ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/ KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/ KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [/ NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **giriş** özellik sayfası.  
  
4.  Değiştirme **yönetilen kaynak dosyası ekleme** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)