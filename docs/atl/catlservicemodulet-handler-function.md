---
title: CAtlServiceModuleT::Handler işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule::Handler
- CServiceModule.Handler
- Handler
dev_langs:
- C++
helpviewer_keywords:
- Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dbc7c74e0fd6fdd34ba9a0c386c028469113c88e
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767095"
---
# <a name="catlservicemodulethandler-function"></a>CAtlServiceModuleT::Handler işlevi

`CAtlServiceModuleT::Handler` Hizmet Denetimi Yöneticisi (SCM) (örneğin, durdurma veya duraklatma) çeşitli yönergeler verir ve hizmet durumunu almak için çağırdığı yordamdır. Bir işlem kodu için SCM geçirir `Handler` hizmet ne yapması gerektiğini belirtmek için. ATL tarafından oluşturulan varsayılan hizmet durdurma yönergesi yalnızca işler. SCM durdurma yönerge geçerse, service, SCM program durmak için olduğunu söyler. Sonra hizmeti çağırır `PostThreadMessage` kendisine bir çıkış iletisi göndermek için. Bu ileti döngüsü sonlanır ve hizmet sonuçta kapatın.

Daha fazla yönerge işlemek için değiştirmeniz gerekir `m_status` veri üyesi başlatıldı olarak `CAtlServiceModuleT` Oluşturucusu. Bu veri üyesi düğmeleri hizmetinin Hizmetler Denetim Masası uygulamasında seçildiğinde etkinleştirmek için SCM söyler.

## <a name="see-also"></a>Ayrıca Bkz.

[Hizmetleri](../atl/atl-services.md)   
[CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)

