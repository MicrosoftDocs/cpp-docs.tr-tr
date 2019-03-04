---
title: CAtlServiceModuleT::Handler işlevi
ms.date: 11/04/2016
f1_keywords:
- CServiceModule::Handler
- CServiceModule.Handler
- Handler
helpviewer_keywords:
- Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
ms.openlocfilehash: e344fd36ad6c70a80486eef6a10eacd8a88a2baf
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273380"
---
# <a name="catlservicemodulethandler-function"></a>CAtlServiceModuleT::Handler işlevi

`CAtlServiceModuleT::Handler` Hizmet Denetimi Yöneticisi (SCM) (örneğin, durdurma veya duraklatma) çeşitli yönergeler verir ve hizmet durumunu almak için çağırdığı yordamdır. Bir işlem kodu için SCM geçirir `Handler` hizmet ne yapması gerektiğini belirtmek için. ATL tarafından oluşturulan varsayılan hizmet durdurma yönergesi yalnızca işler. SCM durdurma yönerge geçerse, service, SCM program durmak için olduğunu söyler. Sonra hizmeti çağırır `PostThreadMessage` kendisine bir çıkış iletisi göndermek için. Bu ileti döngüsü sonlanır ve hizmet sonuçta kapatın.

Daha fazla yönerge işlemek için değiştirmeniz gerekir `m_status` veri üyesi başlatıldı olarak `CAtlServiceModuleT` Oluşturucusu. Bu veri üyesi düğmeleri hizmetinin Hizmetler Denetim Masası uygulamasında seçildiğinde etkinleştirmek için SCM söyler.

## <a name="see-also"></a>Ayrıca bkz.

[Hizmetler](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)
