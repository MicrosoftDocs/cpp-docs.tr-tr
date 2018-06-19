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
ms.openlocfilehash: a0c0386cd17e7a33628790520e356c706f9743b9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355000"
---
# <a name="catlservicemodulethandler-function"></a>CAtlServiceModuleT::Handler işlevi
`CAtlServiceModuleT::Handler` hizmetinin durumunu almak ve (örneğin, durdurma veya duraklatma) çeşitli yönergeler vermek için Hizmet Denetimi Yöneticisi (SCM) çağırır yordamdır. Bir işlem kodu SCM geçirir `Handler` hizmet ne yapması gerektiğini belirtmek için. ATL oluşturulan varsayılan hizmet durdurma yönerge yalnızca işler. SCM Dur yönerge geçerse, hizmet SCM program durmak olduğunu söyler. Hizmeti daha sonra çağırır `PostThreadMessage` kendisine çıkma iletisi göndermek için. Bu ileti döngüsü sona erer ve hizmet sonuçta kapatılacak.  
  
 Daha fazla yönerge işlemek için değiştirmeniz gerekir `m_status` veri üyesi başlatıldı `CAtlServiceModuleT` Oluşturucusu. Bu veri üyesi SCM hizmet hizmetler Denetim Masası uygulamasında seçildiğinde etkinleştirmek için hangi düğmeleri söyler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizmetleri](../atl/atl-services.md)   
 [CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)

