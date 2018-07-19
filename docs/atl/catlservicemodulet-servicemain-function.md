---
title: CAtlServiceModuleT::ServiceMain işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- ServiceMain
- CServiceModule::ServiceMain
- CServiceModule.ServiceMain
dev_langs:
- C++
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9dff3fa3f3ed20406955570f2ad72531f4e44f11
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848127"
---
# <a name="catlservicemoduletservicemain-function"></a>CAtlServiceModuleT::ServiceMain işlevi
Hizmet Denetimi Yöneticisi (SCM) çağıran `ServiceMain` Hizmetler Denetim Masası uygulamasına açtığınızda, hizmeti seçin ve tıklayın **Başlat**.  
  
 SCM sonra çağıran `ServiceMain`, hizmet bir işleyici işlevi SCM vermeniz gerekir. Bu işlev, hizmetin durum elde edilir ve özel yönergeler (örneğin, duraklatmak veya durdurma) geçirmeniz SCM sağlar. Hizmet başarılı olduğunda bu işlev SCM alır `_Handler` Win32 API işlevi [RegisterServiceCtrlHandler](http://msdn.microsoft.com/library/windows/desktop/ms685054). (`_Handler` statik olmayan üye işlevi çağıran bir statik üye işlevi olan [işleyici](../atl/reference/catlservicemodulet-class.md#handler).)  
  
 Başlangıçta, bir hizmet de geçerli durumunu SCM bilgilendirmek. Bunu SERVICE_START_PENDING Win32 API işleve geçirerek yapar [artırılmış](http://msdn.microsoft.com/library/windows/desktop/ms686241).  
  
 `ServiceMain` Daha sonra çağırır `CAtlExeModuleT::InitializeCom`, Win32 API işlevi çağırır [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279). Varsayılan olarak, `InitializeCom` COINIT_MULTITHREADED bayrağı işleve geçirir. Bu bayrak, program ücretsiz iş parçacıklı bir sunucu olduğunu gösterir.  
  
 Şimdi, `CAtlServiceModuleT::Run` hizmet ana iş gerçekleştirmek üzere çağırılır. `Run` Hizmet durduruluncaya kadar yürütmeye devam eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizmetleri](../atl/atl-services.md)   
 [CAtlServiceModuleT::ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)

