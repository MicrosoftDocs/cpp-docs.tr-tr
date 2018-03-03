---
title: "MIDL özellik sayfaları: Gelişmiş | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCMidlTool.ErrorCheckBounds
- VC.Project.VCMidlTool.ErrorCheckStubData
- VC.Project.VCMidlTool.ErrorCheckAllocations
- VC.Project.VCMidlTool.CPreprocessOptions
- VC.Project.VCMidlTool.UndefinePreprocessorDefinitions
- VC.Project.VCMidlTool.EnableErrorChecks
- VC.Project.VCMidlTool.RedirectOutputAndErrors
- VC.Project.VCMidlTool.ErrorCheckEnumRange
- VC.Project.VCMidlTool.StructMemberAlignment
- VC.Project.VCMidlTool.ErrorCheckRefPointers
- VC.Project.VCMidlTool.ValidateParameters
dev_langs:
- C++
helpviewer_keywords:
- MIDL, property pages
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d6e7dde047c3311c6fd694a91c7a63fcfbcc95d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="midl-property-pages-advanced"></a>MIDL Özellik Sayfaları: Gelişmiş
**Gelişmiş** özellik sayfasında **MIDL** klasörü aşağıdaki MIDL derleyici seçenekleri belirtir:  
  
-   Hata denetimini etkinleştir ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Ayırmalar denetleyin ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Sınır denetim ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Onay Enum aralığı ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Başvuru işaretçileri denetleyin ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Saplama veri denetleyin ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Parametreleri doğrulayın ([/ sağlam](http://msdn.microsoft.com/library/windows/desktop/aa367363)) *  
  
-   Yapı üyesi hizalama ([/Zp](http://msdn.microsoft.com/library/windows/desktop/aa367388))  
  
-   Çıktı yeniden yönlendirme ([/o](http://msdn.microsoft.com/library/windows/desktop/aa367351))  
  
-   C Önişle seçenekleri ([/cpp_opt](http://msdn.microsoft.com/library/windows/desktop/aa367318))  
  
-   Önişlemci tanımları tanımlarını Kaldır ([/U](http://msdn.microsoft.com/library/windows/desktop/aa367373))  
  
 \*/ sağlam yalnızca Windows 2000 veya üstü makine için oluşturulurken kullanılır. ATL projeyi oluşturun ve kullanmak istediğiniz / sağlam, dlldatax.c dosyasında bu satırı değiştirin:  
  
```  
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM  
to   
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM  
```  
  
 Nasıl erişileceği hakkında bilgi için **Gelişmiş** özellik sayfasında **MIDL** klasörü, bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).  
  
 MIDL seçenekleri C++ projeleri için programlı erişim hakkında daha fazla bilgi için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MIDL Özellik Sayfaları](../ide/midl-property-pages.md)