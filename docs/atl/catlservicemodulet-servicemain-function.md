---
title: 'CAtlServiceModuleT:: ServiceMain Işlevi'
ms.date: 11/04/2016
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
ms.openlocfilehash: b79767d4c1696174f90a325ea152ccc7939ed9fe
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491717"
---
# <a name="catlservicemoduletservicemain-function"></a>CAtlServiceModuleT:: ServiceMain Işlevi

Hizmet Denetim Yöneticisi (SCM), Hizmetler `ServiceMain` Denetim Masası uygulamasını açtığınızda çağırır, hizmeti seçin ve **Başlat**' a tıklayın.

SCM çağrıldıktan sonra `ServiceMain`, bir hizmetin SCM 'ye bir işleyici işlevi vermesi gerekir. Bu işlev, SCM 'nin hizmetin durumunu almasına ve belirli yönergeleri geçirmeye (duraklatma veya durdurma gibi) olanak tanır. Hizmet, `_Handler` [RegisterServiceCtrlHandler](/windows/win32/api/winsvc/nf-winsvc-registerservicectrlhandlerw)Win32 API işlevine geçtiğinde SCM bu işlevi alır. (`_Handler` statik olmayan üye işlev [işleyicisini](../atl/reference/catlservicemodulet-class.md#handler)çağıran statik bir üye işlevidir.)

Başlangıçta hizmet, SCM 'yi geçerli durumunun de bilgilendirmelidir. Bunu, [SetServiceStatus](/windows/win32/api/winsvc/nf-winsvc-setservicestatus)wın32 API işlevine SERVICE_START_PENDING geçirerek yapar.

`ServiceMain`ardından, `CAtlExeModuleT::InitializeCom` [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex)Win32 API işlevini çağıran çağırır. Varsayılan olarak, `InitializeCom` işlevine COINIT_MULTITHREADED bayrağını geçirir. Bu bayrak, programın ücretsiz bir iş parçacıklı sunucu olduğunu gösterir.

Şimdi, `CAtlServiceModuleT::Run` hizmetin ana işini gerçekleştirmek için çağrılır. `Run`hizmet durduruluncaya kadar yürütülmeye devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[Hizmetler](../atl/atl-services.md)<br/>
[CAtlServiceModuleT:: ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)
