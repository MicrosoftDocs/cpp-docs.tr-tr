---
title: -DELAYLOAD (yükü içe aktarmayı Geciktir) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /delayload
- VC.Project.VCLinkerTool.DelayLoadDLLS
dev_langs:
- C++
helpviewer_keywords:
- DELAYLOAD linker option
- -DELAYLOAD linker option
- /DELAYLOAD linker option
- delayed loading of DLLs, /DELAYLOAD option
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74d65caa8a0ea140f93bf156e3c14a85232e6e56
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372262"
---
# <a name="delayload-delay-load-import"></a>/DELAYLOAD (Yükü İçe Aktarmayı Geciktir)
```  
/DELAYLOAD:dllname  
```  
  
## <a name="parameters"></a>Parametreler  
 `dllname`  
 Gecikme yükü istediğiniz DLL adı.  
  
## <a name="remarks"></a>Açıklamalar  
 /DELAYLOAD seçeneği tarafından belirtilen DLL'yi `dllname` yalnızca ilk çağrıda DLL işlevinde programına tarafından yüklenecek. Daha fazla bilgi için bkz: [Delay-Loaded DLL'ler için bağlayıcı desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md). Seçtiğiniz gibi sayıda DLL'leri belirtmek için gereken sayıda tekrar bu seçeneği kullanabilirsiniz. Programınızı bağlantı ya da kendi Gecikmeli Yükleme Yardımcısı işlevi uygulayabilir, Delayimp.lib kullanmanız gerekir.  
  
 [/DELAY](../../build/reference/delay-delay-load-import-settings.md) bağlama ve her Gecikmeli yüklenen DLL'i seçeneklerini yükleme seçeneği belirtir.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  İçinde **bağlayıcı** klasöründe seçin **giriş** özellik sayfası.  
  
3.  Değiştirme **yüklü DLL'leri Geciktir** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)