---
title: "-PGD (Profil temelli iyileştirmeler için veritabanını belirt) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.ProfileGuidedDatabase
dev_langs: C++
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 37113ef23adbbb50e36b51ed8ef0035ee20e885e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD (Profil Temelli İyileştirmeler için Veritabanını Belirt)
/ PGD:`filename`  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 `filename`  
 Çalışan program hakkında bilgi tutmak için kullanılan .pgd dosya adını belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanırken [/LTCG:PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md), /PGD varsayılan olmayan ad veya .pgd dosyasının konumunu belirtmek için kullanın. /PGD belirtmezseniz, .pgd dosya adı çıktı dosyası (.exe veya .dll) adı ile aynı olur ve bağlantıyı çağrıldığı aynı dizinde oluşturulur.  
  
 /LTCG:PGOPTIMIZE kullanırken, /PGD en iyi duruma getirilmiş görüntüsü oluşturmak için kullanılacak .pgd dosya adını belirtmek için kullanın.  
  
 Daha fazla bilgi için bkz: [profil temelli iyileştirme](../../build/reference/profile-guided-optimizations.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **bağlayıcı** düğümü.  
  
4.  Seçin **en iyi duruma getirme** özellik sayfası.  
  
5.  Değiştirme **profil destekli veritabanını** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)