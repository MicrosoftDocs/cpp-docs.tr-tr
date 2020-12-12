---
description: 'Hakkında daha fazla bilgi edinin: varsayılan sınıf fabrikası ve toplama modelini değiştirme'
title: Varsayılan sınıf fabrikası ve toplama modelini değiştirme
ms.date: 11/04/2016
helpviewer_keywords:
- CComClassFactory class, making the default
- aggregation [C++], using ATL
- aggregation [C++], aggregation models
- defaults [C++], aggregation model in ATL
- default class factory
- class factories, changing default
- CComCoClass class, default class factory and aggregation model
- default class factory, ATL
- defaults [C++], class factory
ms.assetid: 6e040e95-0f38-4839-8a8b-c9800dd47e8c
ms.openlocfilehash: b25dc1c2cf3378532f02b1c0d5ba56cd43ee4ae4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148284"
---
# <a name="changing-the-default-class-factory-and-aggregation-model"></a>Varsayılan sınıf fabrikası ve toplama modelini değiştirme

ATL, [CComCoClass](../atl/reference/ccomcoclass-class.md) kullanarak nesneniz için varsayılan sınıf fabrikası ve toplama modelini tanımlar. `CComCoClass` Aşağıdaki iki makroyu belirtir:

- [DECLARE_CLASSFACTORY](reference/aggregation-and-class-factory-macros.md#declare_classfactory) Sınıf fabrikasını [CComClassFactory](../atl/reference/ccomclassfactory-class.md)olarak bildirir.

- [declare_aggregatable](reference/aggregation-and-class-factory-macros.md#declare_aggregatable) Nesnenizin toplanabilecek olduğunu bildirir.

Sınıf tanımınızda başka bir makro belirterek, bu varsayılandan birini geçersiz kılabilirsiniz. Örneğin, yerine [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) kullanmak için `CComClassFactory` [DECLARE_CLASSFACTORY2](reference/aggregation-and-class-factory-macros.md#declare_classfactory2) makrosunu belirtin:

[!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/cpp/changing-the-default-class-factory-and-aggregation-model_1.h)]

Bir sınıf fabrikası tanımlayan iki diğer makro [declare_classfactory_auto_thread](reference/aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) ve [DECLARE_CLASSFACTORY_SINGLETON](reference/aggregation-and-class-factory-macros.md#declare_classfactory_singleton).

ATL Ayrıca **`typedef`** varsayılan davranışı uygulamak için mekanizmasını kullanır. Örneğin, DECLARE_AGGREGATABLE makro, **`typedef`** `_CreatorClass` atl içinde başvurulan, daha sonra adlandırılmış bir türü tanımlamak için kullanır. Türetilmiş bir sınıfta, **`typedef`** temel sınıf ile aynı adı kullanarak, **`typedef`** TANıMıNıZı kullanarak atl 'deki sonuçları ve varsayılan davranışı geçersiz kılmayı unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM nesnelerinin temelleri](../atl/fundamentals-of-atl-com-objects.md)<br/>
[Toplama ve sınıf fabrikası makroları](../atl/reference/aggregation-and-class-factory-macros.md)
