---
title: "-WINMDFILE (winmd dosyası belirtin) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
dev_langs: C++
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 153e5c0bd42b6fdba59e309483f25f09b86fe9fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE (winmd Dosyası Belirtin)
Tarafından oluşturulan Windows çalışma zamanı meta verileri (.winmd) çıktı dosyası için dosya adını belirten [/WINMD](../../build/reference/winmd-generate-windows-metadata.md) bağlayıcı seçeneği.  
  
```  
/WINMDFILE:filename  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen değeri kullanmak `filename` varsayılan .winmd dosya adı geçersiz kılmak için (`binaryname`.winmd). İçin ".winmd" eklemeyin fark `filename`.  Birden çok değerleri üzerinde listeleniyorsa **/WINMDFILE** komut satırı sonuncu önceliklidir.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **bağlayıcı** klasör.  
  
3.  Seçin **Windows meta verileri** özellik sayfası.  
  
4.  İçinde **Windows meta veri dosyası** kutusuna, dosya konumu girin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ WINMD (Windows meta verileri oluşturun)](../../build/reference/winmd-generate-windows-metadata.md)   
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)