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
ms.openlocfilehash: 8f6ff5a0fdcff62d62469f17388f633b83739a09
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850832"
---
# <a name="creating-an-aggregated-object"></a>Toplanan nesne oluşturma
Toplama Temsilciler `IUnknown` çağrıları, dış nesnenin bir işaretçi sağlayan `IUnknown` iç nesne.  
  
### <a name="to-create-an-aggregated-object"></a>Toplanan nesne oluşturma  
  
1.  Ekleme bir `IUnknown` sınıfınıza işaretçi nesnesinin ve oluşturucuda NULL olarak başlatın.  
  
2.  Geçersiz kılma [FinalConstruct](../atl/reference/ccomobjectrootex-class.md#finalconstruct) toplama oluşturmak için.  
  
3.  Kullanım `IUnknown` işaretçisi, ikinci parametre olarak 1. adımda tanımlanan [COM_INTERFACE_ENTRY_AGGREGATE](reference/com-interface-entry-macros.md#com_interface_entry_aggregate) makroları.  
  
4.  Geçersiz kılma [FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease) yayımlamayı `IUnknown` işaretçi.  
  
> [!NOTE]
>  Kullanın ve yayın sırasında toplanan nesne bir arabirimden `FinalConstruct`, eklemeniz gerekir [DECLARE_PROTECT_FINAL_CONSTRUCT](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct) Makro tanımında sınıfı nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)

