---
title: "-SWAPRUN (çıktıyı takas dosyasına yükle bağlayıcı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.SwapRunFromNet
- /swaprun
- VC.Project.VCLinkerTool.SwapRunFromCD
dev_langs: C++
helpviewer_keywords:
- -SWAPRUN linker option
- files [C++], LINK
- LINK tool [C++], output
- linker [C++], copying output to swap file
- swap file for linker output
- output files, linker
- /SWAPRUN linker option
- SWAPRUN linker option
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f41a89e74ec2e9ed34e0add12717dd0c135ce723
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN (Bağlayıcı Çıktısını Takas Dosyasına Yükle)
```  
/SWAPRUN:{NET|CD}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 /SWAPRUN seçenek ilk kopyayı işletim sistemine bir takas dosyasına çıkarmak ve görüntünün oradan çalıştırın bağlayıcı söyler. Bu bir Windows NT 4.0 (ve üstü) güvenlik özelliğidir.  
  
 NET belirtilirse, işletim sistemi ilk ikili görüntü ağdan bir takas dosyasına kopyalayın ve buradan yükleyebilirsiniz. Bu seçenek, ağ üzerinden uygulamalarını çalıştırmak için yararlıdır. CD belirtildiğinde, işletim sistemi görüntü çıkarılabilir disk üzerindeki bir sayfa dosyasına kopyalayın ve sonra da yükleyin.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **sistem** özellik sayfası.  
  
4.  Aşağıdaki özelliklerden birini değiştirin:  
  
    -   **CD'den Çalıştırma değiştirme**  
  
    -   **Ağ üzerinden çalıştırma değiştirme**  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A> özellikleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)