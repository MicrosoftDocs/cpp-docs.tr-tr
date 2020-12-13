---
description: 'Hakkında daha fazla bilgi edinin: toplanmış nesne oluşturma'
title: Toplanmış nesne oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
ms.openlocfilehash: e6efbf63e28d0477730a2d7c31ec91e9b75520e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153232"
---
# <a name="creating-an-aggregated-object"></a>Toplanmış nesne oluşturma

Toplama temsilcileri `IUnknown` , dış nesnenin iç nesnesine bir işaretçi sağlayarak çağırır `IUnknown` .

## <a name="to-create-an-aggregated-object"></a>Toplanmış bir nesne oluşturmak için

1. `IUnknown`Sınıf nesneniz için bir işaretçi ekleyin ve oluşturucuda null olarak başlatın.

1. Toplama oluşturmak için [Finalyapısını](../atl/reference/ccomobjectrootex-class.md#finalconstruct) geçersiz kılın.

1. `IUnknown` [COM_INTERFACE_ENTRY_AGGREGATE](reference/com-interface-entry-macros.md#com_interface_entry_aggregate) makrolarının Ikinci parametresi olarak adım 1 ' de tanımlanan işaretçiyi kullanın.

1. İşaretçiyi serbest bırakmak için [FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease) 'i geçersiz kılın `IUnknown` .

> [!NOTE]
> Sırasında toplanmış nesneden bir arabirim kullanırsanız ve serbest bırakırsanız `FinalConstruct` , sınıf nesnenizin tanımına [DECLARE_PROTECT_FINAL_CONSTRUCT](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct) makrosunu eklemeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM nesnelerinin temelleri](../atl/fundamentals-of-atl-com-objects.md)
