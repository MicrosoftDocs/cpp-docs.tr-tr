---
title: CAtlServiceModuleT::ServiceMain işlevi
ms.date: 11/04/2016
f1_keywords:
- ServiceMain
- CServiceModule::ServiceMain
- CServiceModule.ServiceMain
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
ms.openlocfilehash: 3aad67d58ccd4d1d35572542d899c17e0f42902b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471220"
---
# <a name="catlservicemoduletservicemain-function"></a>CAtlServiceModuleT::ServiceMain işlevi

Hizmet Denetimi Yöneticisi (SCM) çağıran `ServiceMain` Hizmetler Denetim Masası uygulamasına açtığınızda, hizmeti seçin ve tıklayın **Başlat**.

SCM sonra çağıran `ServiceMain`, hizmet bir işleyici işlevi SCM vermeniz gerekir. Bu işlev, hizmetin durum elde edilir ve özel yönergeler (örneğin, duraklatmak veya durdurma) geçirmeniz SCM sağlar. Hizmet başarılı olduğunda bu işlev SCM alır `_Handler` Win32 API işlevi [RegisterServiceCtrlHandler](/windows/desktop/api/winsvc/nf-winsvc-registerservicectrlhandlera). (`_Handler` statik olmayan üye işlevi çağıran bir statik üye işlevi olan [işleyici](../atl/reference/catlservicemodulet-class.md#handler).)

Başlangıçta, bir hizmet de geçerli durumunu SCM bilgilendirmek. Bunu SERVICE_START_PENDING Win32 API işleve geçirerek yapar [artırılmış](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus).

`ServiceMain` Daha sonra çağırır `CAtlExeModuleT::InitializeCom`, Win32 API işlevi çağırır [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex). Varsayılan olarak, `InitializeCom` COINIT_MULTITHREADED bayrağı işleve geçirir. Bu bayrak, program ücretsiz iş parçacıklı bir sunucu olduğunu gösterir.

Şimdi, `CAtlServiceModuleT::Run` hizmet ana iş gerçekleştirmek üzere çağırılır. `Run` Hizmet durduruluncaya kadar yürütmeye devam eder.

## <a name="see-also"></a>Ayrıca Bkz.

[Hizmetler](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)

