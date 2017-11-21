---
title: "CAtlServiceModuleT::Handler işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CServiceModule::Handler
- CServiceModule.Handler
- Handler
dev_langs: C++
helpviewer_keywords: Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9f8c83db3f7834c79656adc3443fd3c8946a4176
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="catlservicemodulethandler-function"></a>CAtlServiceModuleT::Handler işlevi
`CAtlServiceModuleT::Handler`hizmetinin durumunu almak ve (örneğin, durdurma veya duraklatma) çeşitli yönergeler vermek için Hizmet Denetimi Yöneticisi (SCM) çağırır yordamdır. Bir işlem kodu SCM geçirir `Handler` hizmet ne yapması gerektiğini belirtmek için. ATL oluşturulan varsayılan hizmet durdurma yönerge yalnızca işler. SCM Dur yönerge geçerse, hizmet SCM program durmak olduğunu söyler. Hizmeti daha sonra çağırır `PostThreadMessage` kendisine çıkma iletisi göndermek için. Bu ileti döngüsü sona erer ve hizmet sonuçta kapatılacak.  
  
 Daha fazla yönerge işlemek için değiştirmeniz gerekir `m_status` veri üyesi başlatıldı `CAtlServiceModuleT` Oluşturucusu. Bu veri üyesi SCM hizmet hizmetler Denetim Masası uygulamasında seçildiğinde etkinleştirmek için hangi düğmeleri söyler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizmetleri](../atl/atl-services.md)   
 [CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)

