---
title: "-KEYFILE (derlemeyi imzalamak için anahtar veya anahtar çiftini belirt) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /keyfile
- VC.Project.VCLinkerTool.KeyFile
dev_langs: C++
helpviewer_keywords:
- /KEYFILE linker option
- -KEYFILE linker option
- KEYFILE linker option
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86457510eb017fe2d5060f2f37661a3397ec30d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="keyfile-specify-key-or-key-pair-to-sign-an-assembly"></a>/KEYFILE (Derlemeyi İmzalamak için Anahtar veya Anahtar Çiftini Belirt)
```  
/KEYFILE:filename  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *Dosya adı*  
 Anahtarı içeren dosya. Dize çift tırnak içine yerleştirin ("") boşluk içeriyorsa.  
  
## <a name="remarks"></a>Açıklamalar  
 Bağlayıcı derleme bildirimine ortak anahtar ekler ve ardından son derlemeyi özel anahtarıyla imzalar. Bir anahtar dosyası oluşturmak için şunu yazın [sn -k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* komut satırında. İmzalı bir derleme tanımlayıcı adı kabul edilir.  
  
 İle derleme yaparsanız [/LN](../../build/reference/ln-create-msil-module.md), anahtar dosyasının adı modülde tutulur ve aracılığıyla modülü için açık bir başvuru içeren bir derleme derlediğinizde oluşturduğunuz derlemesini birleştirilmiş [#using](../../preprocessor/hash-using-directive-cpp.md), veya ile bağlarken [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).  
  
 Bağlayıcı ile için şifreleme bilgilerinizi geçirebilirsiniz [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md). Kullanım [/delaysign](../../build/reference/delaysign-partially-sign-an-assembly.md) kısmen imzalı bir derleme istiyorsanız. Bkz: [tanımlayıcı ad derlemeleri (derleme imzalama) (C + +/ CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) derleme imzalama hakkında daha fazla bilgi için.  
  
 İçinde her ikisi de case **/keyfile** ve **/keycontainer** belirtilir (komut satırı seçeneği veya özel özniteliği tarafından), bağlayıcı ilk anahtar kapsayıcısı deneyin. Bu başarılı olursa, derleme anahtar kapsayıcısı içindeki bilgilerle imzalanır. Bağlayıcı anahtar kapsayıcısını bulamazsa/keyfile ile belirtilen dosyayı çalışacaktır. Bu başarılı olursa, derleme anahtar dosyası içindeki bilgilerle imzalanır ve anahtar bilgileri anahtar kapsayıcısında yüklenecek (sn benzer -i) sonraki derlemede anahtar kapsayıcısı geçerli olmayacaktır.  
  
 Bir anahtar dosyası yalnızca ortak anahtar içerebileceğini unutmayın.  
  
 Bkz: [bkz](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies) derleme imzalama hakkında daha fazla bilgi için.  
  
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