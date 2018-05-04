---
title: -DEF (modül tanım dosyasını belirt) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ModuleDefinitionFile
- /def
dev_langs:
- C++
helpviewer_keywords:
- module definition files, specifying
- DEF linker option
- -DEF linker option
- module definition files
- /DEF linker option
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0c712b81fbb755edd132c6f97efc906ba4f5ff9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="def-specify-module-definition-file"></a>/DEF (Modül Tanım Dosyasını Belirt)
```  
/DEF:filename  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *Dosya adı*  
 Bir modül tanım dosyasını bağlayıcıya geçirilecek (.def) adı.  
  
## <a name="remarks"></a>Açıklamalar  
 / DEF seçeneği modül tanım dosyasını (.def) bağlayıcıya geçirir. Yalnızca bir .def dosyası bağlantı belirtilebilir. .Def dosyaları hakkında daha fazla ayrıntı için bkz: [modül tanımı dosyaları](../../build/reference/module-definition-dot-def-files.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **giriş** özellik sayfası.  
  
4.  Değiştirme **modül tanım dosyası** özelliği.  
  
 Geliştirme ortamında bir .def dosyası belirtmek için diğer dosyaların yanı sıra projeye ekleyin ve/DEF seçeneği dosyasına belirtmeniz gerekir.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)