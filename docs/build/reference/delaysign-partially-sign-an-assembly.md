---
title: "-DELAYSIGN (derlemeyi kısmen imzala) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /delaysign
- VC.Project.VCLinkerTool.DelaySign
dev_langs:
- C++
helpviewer_keywords:
- /DELAYSIGN linker option
- DELAYSIGN linker option
- -DELAYSIGN linker option
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f67e4da2d85d94854ec0802450b41333d6577175
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="delaysign-partially-sign-an-assembly"></a>/DELAYSIGN (Derlemeyi Kısmen İmzala)
```  
/DELAYSIGN[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 YOK  
 Derleme değil kısmen imzalanması gerektiğini belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım **/delaysign** yalnızca ortak anahtar derlemede yerleştirmek istiyorsanız. Varsayılan değer **/DELAYSIGN:NO**.  
  
 **/Delaysign** seçeneği hiçbir etkisi ile kullanılmadığı sürece [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) veya [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md).  
  
 Tam imzalı bir derleme istediğinde bildirimi (derleme meta verilerini) içeren ve karmayı özel anahtarıyla imzalar dosyayı derleyici karma hale getirir. Elde edilen dijital imza, bildirimi içeren dosyada depolanır. Bir derlemeyi imzalı gecikme olduğunda, bağlayıcı işlem değil ve daha sonra imzanın eklenmesi için imza ancak yer ayırır dosyasında depolamak.  
  
 Örneğin, kullanarak **/delaysign** genel önbelleğinde derleme yerleştirilecek tester sağlar. Test sonra özel anahtarı derlemeye koyarak derleme tam olarak oturum açabilir.  
  
 Bkz: [tanımlayıcı ad derlemeleri (derleme imzalama) (C + +/ CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) ve [Gecikmeli bir derleme imzalama](/dotnet/framework/app-domains/delay-sign-assembly) derleme imzalama hakkında daha fazla bilgi için.  
  
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