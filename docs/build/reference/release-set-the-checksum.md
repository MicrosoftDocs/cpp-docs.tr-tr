---
title: "-RELEASE (sağlama toplamını Ayarla) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /release
- VC.Project.VCLinkerTool.SetChecksum
dev_langs: C++
helpviewer_keywords:
- -RELEASE linker option
- /RELEASE linker option
- checksum setting
- RELEASE linker option
ms.assetid: 93bcadf4-29ac-4824-914b-6997e3751d22
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5f561d96d46fadd24bc6dd7a4d473f3fcdc3bec7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="release-set-the-checksum"></a>/RELEASE (Sağlama Toplamını Ayarla)
```  
/RELEASE  
```  
  
## <a name="remarks"></a>Açıklamalar  
 / Release seçeneği bir .exe dosyası üstbilgisinde sağlama toplamı ayarlar.  
  
 İşletim sistemi sağlama toplamı aygıt sürücülerini gerektirir. Gelecekteki işletim sistemleri ile uyumluluğu sağlamak için sağlama toplamı, aygıt sürücülerinin yayın sürümünü ayarlayın.  
  
 / Release seçeneği varsayılan olarak ayarlanır, [/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) seçeneği belirtildi.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **Gelişmiş** özellik sayfası.  
  
4.  Değiştirme **kümesi sağlama toplamı** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)