---
title: -FIXED (sabit temel adres) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fixed
- VC.Project.VCLinkerTool.FixedBaseAddress
dev_langs:
- C++
helpviewer_keywords:
- preferred base address for loading program
- /FIXED linker option
- -FIXED linker option
- FIXED linker option
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08b1193b7cfe58aed45e4feec598a49227eafc87
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374167"
---
# <a name="fixed-fixed-base-address"></a>/FIXED (Sabit Temel Adres)
```  
/FIXED[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Programı yalnızca, tercih edilen temel adres yüklenecek işletim sistemini söyler. Tercih edilen temel adres kullanılamıyorsa, işletim sistemi dosya yüklemez. Daha fazla bilgi için bkz: [/BASE (Temel adres)](../../build/reference/base-base-address.md).  
  
 DLL ve /FIXED için herhangi bir proje türü için varsayılan /FIXED:NO varsayılan ayardır.  
  
 BAĞLANTI /FIXED belirtildiğinde, yeniden konumlandırma bölüm programa oluşturmaz. Çalışma zamanında, işletim sistemi programın belirtilen adresteki yükleyemiyor ise, bir hata iletisi sorunları ve program yüklemez.  
  
 Programa yeniden konumlandırma bölüm oluşturmak için /FIXED:NO belirtin.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **bağlayıcı** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  Seçenek adı yazın ve ayarı **ek seçenekler** kutusu.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)