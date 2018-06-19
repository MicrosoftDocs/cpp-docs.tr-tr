---
title: -MAPINFO (bilgileri eşlem dosyasına dahil et) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.MapLines
- VC.Project.VCLinkerTool.MapInfoFixups
- VC.Project.VCLinkerTool.MapExports
- /mapinfo
dev_langs:
- C++
helpviewer_keywords:
- /MAPINFO linker option
- MAPINFO linker option
- -MAPINFO linker option
ms.assetid: 533d2bce-f9b7-4fea-ae1c-0b4864c9d10b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c65a3c546b808b9a899280933c813422a967f78a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373367"
---
# <a name="mapinfo-include-information-in-mapfile"></a>/MAPINFO (Bilgileri Eşlem Dosyasına Dahil Et)
```  
/MAPINFO:EXPORTS  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen bilgileri belirtirseniz, oluşturulan bir eşlem dosyasına dahil etmek için bağlayıcı /MAPINFO seçenek söyler [/MAP](../../build/reference/map-generate-mapfile.md) seçeneği.  Dışarı aktarma, dışarı aktarılan işlevler eklemek için bağlayıcı söyler.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **hata ayıklama** özellik sayfası.  
  
4.  Değişiklik **harita dışarı** özellikleri:  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapExports%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)