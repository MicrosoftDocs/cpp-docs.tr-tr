---
title: -WINMDKEYFILE (winmd anahtar dosyası belirtin) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKeyFile
dev_langs:
- C++
ms.assetid: 65d88fdc-fff9-49ea-8cfc-b2f408741734
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba19ddd7a9ca1c313cc9f72e6cc8b77b4b565ceb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="winmdkeyfile-specify-winmd-key-file"></a>/WINMDKEYFILE (winmd Anahtar Dosyası Belirtin)
Bir anahtar veya bir Windows çalışma zamanı meta verileri (.winmd) dosyasını imzalamak için bir anahtar çifti belirtir.  
  
```  
/WINMDKEYFILE:filename  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Benzer [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) .winmd dosyaya uygulanan bağlayıcı seçeneği.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **bağlayıcı** klasör.  
  
3.  Seçin **Windows meta verileri** özellik sayfası.  
  
4.  İçinde **Windows meta veri anahtar dosyası** kutusuna, dosya konumu girin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)