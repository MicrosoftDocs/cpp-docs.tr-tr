---
title: "CAtlServiceModuleT::ServiceMain işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ServiceMain
- CServiceModule::ServiceMain
- CServiceModule.ServiceMain
dev_langs: C++
helpviewer_keywords: ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 633e9bc4689ced93e1c22151b32654f7ae9d7ece
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="catlservicemoduletservicemain-function"></a>CAtlServiceModuleT::ServiceMain işlevi
Hizmet Denetimi Yöneticisi (SCM) çağırır `ServiceMain` Hizmetleri Denetim Masası uygulaması açtığınızda, hizmeti seçin ve'ı tıklatın **Başlat**.  
  
 SCM sonra çağırır `ServiceMain`, bir hizmet SCM bir işleyici işlevi vermeniz gerekir. Bu işlev hizmetin durumunu elde edilir ve (örneğin, duraklatmak veya durduruluyor) yönelik özel yönergeler geçirmek SCM sağlar. Hizmet başarılı olduğunda bu işlev SCM alır **_Handler** Win32 API işlevi [RegisterServiceCtrlHandler](http://msdn.microsoft.com/library/windows/desktop/ms685054). (**_Handler** statik olmayan üye işlevi çağıran bir statik üye işlevi [işleyici](../atl/reference/catlservicemodulet-class.md#handler).)  
  
 Başlangıçta, bir hizmet ayrıca geçerli durumunu SCM bildirin. Bunu geçirerek yapar **SERVICE_START_PENDING** Win32 API işlevi [artırılmış](http://msdn.microsoft.com/library/windows/desktop/ms686241).  
  
 `ServiceMain`Daha sonra çağırır `CAtlExeModuleT::InitializeCom`, Win32 API işlev çağrılarını [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279). Varsayılan olarak, `InitializeCom` geçirir **COINIT_MULTITHREADED** işlevi için bayrak. Bu bayrak program bir ücretsiz iş parçacıklı sunucusu olarak gösterir.  
  
 Şimdi, `CAtlServiceModuleT::Run` ana iş hizmetinin gerçekleştirmek üzere çağırılır. **Çalıştırma** Hizmet durduruluncaya kadar yürütmeye devam eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizmetleri](../atl/atl-services.md)   
 [CAtlServiceModuleT::ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)

