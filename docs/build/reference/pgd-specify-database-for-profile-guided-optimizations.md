---
title: "-PGD (Profil temelli iyileştirmeler için veritabanını belirt) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
dev_langs:
- C++
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cb61395d9f3b8c98e17e3683a7c3897b9315d78b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)