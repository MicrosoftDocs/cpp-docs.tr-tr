---
title: "-WINMDKEYCONTAINER (anahtar kapsayıcısı belirtin) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
dev_langs:
- C++
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cfb71a932180a41784b9e0894220982a170e6bf2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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