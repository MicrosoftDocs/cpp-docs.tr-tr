---
title: -WINMDKEYCONTAINER (anahtar kapsayıcısı belirtin) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
dev_langs:
- C++
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36e4f74eb249c2687716fedb43ccf0a37e35f7b7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376617"
---
# <a name="winmdkeycontainer-specify-key-container"></a>/WINMDKEYCONTAINER (Tanımlayıcı Ad Anahtar Kapsayıcısı Belirtin)
Bir Windows Meta veriler (.winmd) dosyasını imzalamak için anahtar kapsayıcısını belirtir.  
  
```  
/WINMDKEYCONTAINER:name  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Benzer [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md) (.winmd) dosyaya uygulanan bağlayıcı seçeneği.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **bağlayıcı** klasör.  
  
3.  Seçin **Windows meta verileri** özellik sayfası.  
  
4.  İçinde **Windows meta verileri anahtar kapsayıcısı** kutusunda, konumu girin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)