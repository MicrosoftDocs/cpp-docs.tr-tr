---
title: Toplanan nesne oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
ms.openlocfilehash: 5c655b8ced7738b30bf13d088cfadf11b5c65ef0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449861"
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

## <a name="see-also"></a>Ayrıca Bkz.

[ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)

