---
title: Toplanan nesne oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35ddbd6b8db853967a70de0427cc842689d55c82
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="creating-an-aggregated-object"></a>Toplanan nesne oluşturma
Toplama Temsilciler **IUnknown** çağrıları, dış nesnenin gösteren bir işaretçi sağlama **IUnknown** iç nesne.  
  
### <a name="to-create-an-aggregated-object"></a>Toplanan nesne oluşturmak için  
  
1.  Ekleme bir **IUnknown** işaretçi sınıfınıza nesne ve ona başlatma **NULL** oluşturucuda.  
  
2.  Geçersiz kılma [FinalConstruct](../atl/reference/ccomobjectrootex-class.md#finalconstruct) toplama oluşturmak için.  
  
3.  Kullanım **IUnknown** işaretçi, adım 1'de, ikinci parametre için tanımlanan [COM_INTERFACE_ENTRY_AGGREGATE](reference/com-interface-entry-macros.md#com_interface_entry_aggregate) makroları.  
  
4.  Geçersiz kılma [FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease) yayımlamayı **IUnknown** işaretçi.  
  
> [!NOTE]
>  Kullanın ve yayın sırasında toplanan nesneden bir arabirim `FinalConstruct`, eklemelisiniz [DECLARE_PROTECT_FINAL_CONSTRUCT](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct) sınıfı nesnesinin tanımı makrosuna.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)

