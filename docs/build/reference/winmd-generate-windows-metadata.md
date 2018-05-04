---
title: -WINMD (Windows meta verileri oluşturun) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs:
- C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d3e628713c8228675db3b34e70d670c88152462
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (Windows Meta Verileri Oluşturun)
Windows çalışma zamanı meta veri (.winmd) dosyası olarak oluşturulmasını sağlar.  
  
```  
/WINMD[:{NO|ONLY}]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 / WINMD  
 Evrensel Windows platformu uygulamaları için varsayılan ayar. Bağlayıcı ikili yürütülebilir dosyasının hem .winmd meta veri dosyası oluşturur.  
  
 /WINMD:NO  
 Bağlayıcı, yalnızca ikili yürütülebilir dosyası, ancak .winmd dosyası oluşturur.  
  
 / WINMD: YALNIZCA  
 Bağlayıcı, yalnızca .winmd dosyası ancak değil ikili yürütülebilir dosyası oluşturur.  
  
 Varsayılan olarak, çıktı dosyası adını formun sahip `binaryname`.winmd. Farklı bir dosya adı belirtmek için kullanın [/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md) seçeneği.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **bağlayıcı** klasör.  
  
3.  Seçin **Windows meta verileri** özellik sayfası.  
  
4.  İçinde **oluşturmak Windows Meta** aşağı açılan liste kutusunda, kullanmak istediğiniz seçeneği seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)