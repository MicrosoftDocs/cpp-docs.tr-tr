---
title: Toplanan nesne oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
ms.openlocfilehash: 4be8d0e852da91b58125dc01d44eed4560b2b8d9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57277527"
---
# <a name="creating-an-aggregated-object"></a>Toplanan nesne oluşturma

Toplama Temsilciler `IUnknown` çağrıları, dış nesnenin bir işaretçi sağlayan `IUnknown` iç nesne.

## <a name="to-create-an-aggregated-object"></a>Toplanan nesne oluşturma

1. Ekleme bir `IUnknown` sınıfınıza işaretçi nesnesinin ve oluşturucuda NULL olarak başlatın.

1. Geçersiz kılma [FinalConstruct](../atl/reference/ccomobjectrootex-class.md#finalconstruct) toplama oluşturmak için.

1. Kullanım `IUnknown` işaretçisi, ikinci parametre olarak 1. adımda tanımlanan [COM_INTERFACE_ENTRY_AGGREGATE](reference/com-interface-entry-macros.md#com_interface_entry_aggregate) makroları.

1. Geçersiz kılma [FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease) yayımlamayı `IUnknown` işaretçi.

> [!NOTE]
> Kullanın ve yayın sırasında toplanan nesne bir arabirimden `FinalConstruct`, eklemeniz gerekir [DECLARE_PROTECT_FINAL_CONSTRUCT](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct) Makro tanımında sınıfı nesne.

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)
