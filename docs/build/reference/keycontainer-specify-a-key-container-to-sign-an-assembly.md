---
title: -KEYCONTAINER (derlemeyi imzalamak için anahtar kapsayıcısını belirt) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.KeyContainer
- /keycontainer
dev_langs:
- C++
helpviewer_keywords:
- KEYCONTAINER linker option
- /KEYCONTAINER linker option
- -KEYCONTAINER linker option
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13058978b0833a17abbbfb68a2ed753aacfb6d49
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377893"
---
# <a name="keycontainer-specify-a-key-container-to-sign-an-assembly"></a>/KEYCONTAINER (Derlemeyi İmzalamak için Anahtar Kapsayıcısını Belirt)
```  
/KEYCONTAINER:name  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 *Adı*  
 Anahtarı içeren kapsayıcı. Dize çift tırnak içine yerleştirin ("") boşluk içeriyorsa.  
  
## <a name="remarks"></a>Açıklamalar  
 Bağlayıcı, bir ortak anahtar derleme bildirimine ekleme ve özel anahtarla son derleme imzalama tarafından imzalı bir derleme oluşturur. Bir anahtar dosyası oluşturmak için şunu yazın [sn -k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* komut satırında. **sn -i** anahtar çiftini bir kapsayıcıya yükler.  
  
 İle derleme yaparsanız [/LN](../../build/reference/ln-create-msil-module.md), anahtar dosyasının adı modülde tutulur ve aracılığıyla modülü için açık bir başvuru içeren bir derleme derlediğinizde oluşturduğunuz derlemesini birleştirilmiş [#using](../../preprocessor/hash-using-directive-cpp.md), veya ile bağlarken [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).  
  
 Derleyici ile şifreleme bilgilerinizi geçirebilirsiniz [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md). Kullanım [/delaysign](../../build/reference/delaysign-partially-sign-an-assembly.md) kısmen imzalı bir derleme istiyorsanız. Bkz: [tanımlayıcı ad derlemeleri (derleme imzalama) (C + +/ CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) derleme imzalama hakkında daha fazla bilgi için.  
  
 Derleme oluşturma etkileyen diğer bağlayıcı seçenekleri şunlardır:  
  
-   [/ ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
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