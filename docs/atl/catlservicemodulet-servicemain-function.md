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
ms.openlocfilehash: ae357caad88e128fe9f3742887781d0096efe2c9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058594"
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

