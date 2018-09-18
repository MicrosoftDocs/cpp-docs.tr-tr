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
ms.openlocfilehash: 7c8dc0b0d41a18c775258e1eacddd8e4dbebdb3d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039224"
---
# <a name="catlservicemodulethandler-function"></a>CAtlServiceModuleT::Handler işlevi

`CAtlServiceModuleT::Handler` Hizmet Denetimi Yöneticisi (SCM) (örneğin, durdurma veya duraklatma) çeşitli yönergeler verir ve hizmet durumunu almak için çağırdığı yordamdır. Bir işlem kodu için SCM geçirir `Handler` hizmet ne yapması gerektiğini belirtmek için. ATL tarafından oluşturulan varsayılan hizmet durdurma yönergesi yalnızca işler. SCM durdurma yönerge geçerse, service, SCM program durmak için olduğunu söyler. Sonra hizmeti çağırır `PostThreadMessage` kendisine bir çıkış iletisi göndermek için. Bu ileti döngüsü sonlanır ve hizmet sonuçta kapatın.

Daha fazla yönerge işlemek için değiştirmeniz gerekir `m_status` veri üyesi başlatıldı olarak `CAtlServiceModuleT` Oluşturucusu. Bu veri üyesi düğmeleri hizmetinin Hizmetler Denetim Masası uygulamasında seçildiğinde etkinleştirmek için SCM söyler.

## <a name="see-also"></a>Ayrıca Bkz.

[Hizmetler](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)

