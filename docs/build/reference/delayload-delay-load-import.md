---
title: "-DELAYLOAD (yükü içe aktarmayı Geciktir) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4fd524e72125408c6a88bea83272e18a7ef9b78d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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