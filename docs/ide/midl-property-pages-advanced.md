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
ms.openlocfilehash: ed9d6ba12e65eac325008cb2a448abdab087ee46
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197966"
---
# <a name="midl-property-pages-advanced"></a>MIDL Özellik Sayfaları: Gelişmiş
**Gelişmiş** özellik sayfasında **MIDL** klasörü aşağıdaki MIDL derleyici seçeneklerini belirtir:  
  
-   Hata denetimini etkinleştir ([/Error](https://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Ayrılan alanları denetle ([/Error](https://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Sınırları denetle ([/Error](https://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Sabit listesi aralıklarını denetle ([/Error](https://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Başvuru işaretçilerini denetle ([/Error](https://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Saplama verilerini denetle ([/Error](https://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Parametreleri doğrula ([/ robust](https://msdn.microsoft.com/library/windows/desktop/aa367363)) \*  
  
-   Struct üyesi hizalaması ([/ZP](https://msdn.microsoft.com/library/windows/desktop/aa367388))  
  
-   Çıktı yeniden yönlendirme ([/o](https://msdn.microsoft.com/library/windows/desktop/aa367351))  
  
-   C ön işleme seçenekleri ([/cpp_opt](https://msdn.microsoft.com/library/windows/desktop/aa367318))  
  
-   Ön İşlemci tanımlarını Kaldır ([/U](https://msdn.microsoft.com/library/windows/desktop/aa367373))  
  
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