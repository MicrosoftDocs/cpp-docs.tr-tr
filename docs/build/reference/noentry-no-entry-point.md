---
title: -NOENTRY (giriş noktası yok) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ResourceOnlyDLL
- /noentry
dev_langs:
- C++
helpviewer_keywords:
- entry points [C++], linker specifying
- -NOENTRY linker option
- resource-only DLLs [C++], creating
- NOENTRY linker option
- /NOENTRY linker option [C++]
- DLLs [C++], creating
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 44f35c995a0c839fdc0d4ccf3d286e332793cf70
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374043"
---
# <a name="noentry-no-entry-point"></a>/NOENTRY (Giriş Noktası Yok)
```  
/NOENTRY  
```  
  
## <a name="remarks"></a>Açıklamalar  
 /NOENTRY seçeneği çalıştırılabilir kod içermeyen bir yalnızca kaynak DLL oluşturmak için gereklidir. Daha fazla bilgi için bkz: [Resource-Only DLL oluşturma](../../build/creating-a-resource-only-dll.md).  
  
 Bir başvuru bağlama bağlantı engellemek için bu seçeneği kullanın `_main` DLL içine.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Seçin **bağlayıcı** klasör.  
  
3.  Seçin **Gelişmiş** özellik sayfası.  
  
4.  Değiştirme **No giriş noktası** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yalnızca kaynak DLL oluşturma](../../build/creating-a-resource-only-dll.md)   
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)