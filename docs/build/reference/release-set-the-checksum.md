---
title: -RELEASE (sağlama toplamını Ayarla) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /release
- VC.Project.VCLinkerTool.SetChecksum
dev_langs:
- C++
helpviewer_keywords:
- -RELEASE linker option
- /RELEASE linker option
- checksum setting
- RELEASE linker option
ms.assetid: 93bcadf4-29ac-4824-914b-6997e3751d22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d360ad7264cb66da140df340bc9d281a329c26c2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)