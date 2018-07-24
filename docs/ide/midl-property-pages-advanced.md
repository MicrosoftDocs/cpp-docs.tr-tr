---
title: 'MIDL özellik sayfaları: Gelişmiş | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b99dae277fec7618c2e7caeb76229edce7a78c2
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207766"
---
# <a name="midl-property-pages-advanced"></a>MIDL Özellik Sayfaları: Gelişmiş
**Gelişmiş** özellik sayfasında **MIDL** klasörü aşağıdaki MIDL derleyici seçeneklerini belirtir:  
  
-   Hata denetimini etkinleştir ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Ayrılan alanları denetle ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Sınırları denetle ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Sabit listesi aralıklarını denetle ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Başvuru işaretçilerini denetle ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Saplama verilerini denetle ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Parametreleri doğrula ([/ robust](http://msdn.microsoft.com/library/windows/desktop/aa367363)) \*  
  
-   Struct üyesi hizalaması ([/ZP](http://msdn.microsoft.com/library/windows/desktop/aa367388))  
  
-   Çıktı yeniden yönlendirme ([/o](http://msdn.microsoft.com/library/windows/desktop/aa367351))  
  
-   C ön işleme seçenekleri ([/cpp_opt](http://msdn.microsoft.com/library/windows/desktop/aa367318))  
  
-   Ön İşlemci tanımlarını Kaldır ([/U](http://msdn.microsoft.com/library/windows/desktop/aa367373))  
  
 \* / sağlam yalnızca Windows 2000 veya daha yeni bir makine için oluşturma sırasında kullanılır. Bir ATL projesi oluşturmak ve kullanmak istediğiniz / robust, dlldatax.c dosyasında şu satırı değiştirin:  
  
```  
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM  
to   
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM  
```  
  
 Erişim hakkında daha fazla bilgi için **Gelişmiş** özellik sayfasında **MIDL** klasörüne bakın [Working with Project Properties](../ide/working-with-project-properties.md).  
  
 MIDL seçenekleri C++ projeleri için programlı erişim hakkında daha fazla bilgi için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MIDL Özellik Sayfaları](../ide/midl-property-pages.md)