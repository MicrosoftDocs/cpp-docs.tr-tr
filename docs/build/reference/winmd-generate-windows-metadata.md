---
title: "-WINMD (Windows meta verileri oluşturun) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs:
- C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7517ec459677659067e80930ee48caccf84d52f3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (Windows Meta Verileri Oluşturun)
Windows çalışma zamanı meta veri (.winmd) dosyası olarak oluşturulmasını sağlar.  
  
```  
/WINMD[:{NO|ONLY}]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 /WINMD  
 Evrensel Windows platformu uygulamaları için varsayılan ayar. Bağlayıcı ikili yürütülebilir dosyasının hem .winmd meta veri dosyası oluşturur.  
  
 /WINMD:NO  
 Bağlayıcı, yalnızca ikili yürütülebilir dosyası, ancak .winmd dosyası oluşturur.  
  
 /WINMD:ONLY  
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