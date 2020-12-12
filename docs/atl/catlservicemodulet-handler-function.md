---
description: 'Daha fazla bilgi edinin: CAtlServiceModuleT:: Handler Işlevi'
title: 'CAtlServiceModuleT:: Handler Işlevi'
ms.date: 11/04/2016
helpviewer_keywords:
- Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
ms.openlocfilehash: 934c612b6fdfd47bb9966536cc335da58fbd38c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148375"
---
# <a name="catlservicemodulethandler-function"></a>CAtlServiceModuleT:: Handler Işlevi

`CAtlServiceModuleT::Handler` , hizmet Denetim Yöneticisi 'nin (SCM) hizmet durumunu almak için çağrı yaptığı ve buna çeşitli yönergeler (örneğin, durdurma veya duraklatma) sağlayan yordamdır. SCM, `Handler` hizmetin ne yapması gerektiğini göstermek için bir işlem kodu geçirir. Varsayılan ATL tarafından oluşturulan bir hizmet yalnızca durdurma yönergesini işler. SCM durdurma yönergesini geçerse, hizmet SCM 'ye programın durmak üzere olduğunu söyler. Hizmet daha sonra `PostThreadMessage` bir çıkış iletisi göndermek için çağırır. Bu ileti döngüsünü sonlandırır ve hizmet sonunda kapatılacak.

Daha fazla yönerge işlemek için, `m_status` oluşturucuda başlatılan veri üyesini değiştirmeniz gerekir `CAtlServiceModuleT` . Bu veri üyesi, hizmet Hizmetleri Denetim Masası uygulamasında hizmet seçildiğinde, SCM 'ye hangi düğmelerin etkinleşeceklerini söyler.

## <a name="see-also"></a>Ayrıca bkz.

[Hizmetler](../atl/atl-services.md)<br/>
[CAtlServiceModuleT:: Handler](../atl/reference/catlservicemodulet-class.md#handler)
