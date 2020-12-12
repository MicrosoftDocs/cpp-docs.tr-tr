---
description: 'Daha fazla bilgi edinin: CAtlServiceModuleT:: ServiceMain Işlevi'
title: 'CAtlServiceModuleT:: ServiceMain Işlevi'
ms.date: 11/04/2016
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
ms.openlocfilehash: 97093d13a2f13ea0d6bd4ba5db46bef45d239cc9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148336"
---
# <a name="catlservicemoduletservicemain-function"></a>CAtlServiceModuleT:: ServiceMain Işlevi

Hizmet Denetim Yöneticisi (SCM), `ServiceMain` Hizmetler Denetim Masası uygulamasını açtığınızda çağırır, hizmeti seçin ve **Başlat**' a tıklayın.

SCM çağrıldıktan sonra `ServiceMain` , bir HIZMETIN SCM 'ye bir işleyici işlevi vermesi gerekir. Bu işlev, SCM 'nin hizmetin durumunu almasına ve belirli yönergeleri geçirmeye (duraklatma veya durdurma gibi) olanak tanır. Hizmet, `_Handler` [RegisterServiceCtrlHandler](/windows/win32/api/winsvc/nf-winsvc-registerservicectrlhandlerw)wın32 API işlevine geçtiğinde SCM bu işlevi alır. ( `_Handler` statik olmayan üye Işlev [işleyicisini](../atl/reference/catlservicemodulet-class.md#handler)çağıran statik bir üye işlevidir.)

Başlangıçta hizmet, SCM 'yi geçerli durumunun de bilgilendirmelidir. Bunu, [SetServiceStatus](/windows/win32/api/winsvc/nf-winsvc-setservicestatus)Win32 API işlevine SERVICE_START_PENDING geçirerek yapar.

`ServiceMain` ardından `CAtlExeModuleT::InitializeCom` , [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex)Win32 API işlevini çağıran çağırır. Varsayılan olarak, `InitializeCom` COINIT_MULTITHREADED bayrağını işleve geçirir. Bu bayrak, programın ücretsiz bir iş parçacıklı sunucu olduğunu gösterir.

Şimdi, `CAtlServiceModuleT::Run` hizmetin ana işini gerçekleştirmek için çağrılır. `Run` hizmet durduruluncaya kadar yürütülmeye devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[Hizmetler](../atl/atl-services.md)<br/>
[CAtlServiceModuleT:: ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)
