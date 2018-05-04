---
title: Varsayılan üreteci ve toplama modeli değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce64f2162aa0d5cdf5bcf5e16b56b6989fcaf1ee
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="changing-the-default-class-factory-and-aggregation-model"></a>Varsayılan üreteci ve toplama modelini değiştirme
ATL kullanan [CComCoClass](../atl/reference/ccomcoclass-class.md) , nesne için varsayılan sınıf Fabrika ve toplama modeli tanımlamak için. `CComCoClass` Aşağıdaki iki makroları belirtir:  
  
-   [DECLARE_CLASSFACTORY](reference/aggregation-and-class-factory-macros.md#declare_classfactory) olmasını üreteci bildirir [CComClassFactory](../atl/reference/ccomclassfactory-class.md).  
  
-   [DECLARE_AGGREGATABLE](reference/aggregation-and-class-factory-macros.md#declare_aggregatable) nesnenizin kümelenebilir bildirir.  
  
 Bu varsayılan birini Sınıf tanımınız içinde başka bir makrosu belirterek geçersiz kılabilirsiniz. Örneğin, kullanılacak [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) yerine `CComClassFactory`, belirtin [DECLARE_CLASSFACTORY2](reference/aggregation-and-class-factory-macros.md#declare_classfactory2) makrosu:  
  
 [!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/cpp/changing-the-default-class-factory-and-aggregation-model_1.h)]  
  
 Bir sınıf fabrikası tanımlayın iki makroların [DECLARE_CLASSFACTORY_AUTO_THREAD](reference/aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) ve [DECLARE_CLASSFACTORY_SINGLETON](reference/aggregation-and-class-factory-macros.md#declare_classfactory_singleton).  
  
 ATL de kullanır `typedef` varsayılan davranışı uygulamak için bir mekanizma. Örneğin, `DECLARE_AGGREGATABLE` makrosu kullanan `typedef` adlı tür tanımlamak için **_CreatorClass**, hangi sonra başvurulmaktadır ATL Türetilen bir sınıfta unutmayın bir `typedef` temel sınıfın aynı adı kullanarak `typedef` tanımınızı kullanarak ve varsayılan davranışı geçersiz kılma ATL neden olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM nesneleri temelleri](../atl/fundamentals-of-atl-com-objects.md)   
 [Toplama ve Sınıf Üreticisi Makroları](../atl/reference/aggregation-and-class-factory-macros.md)

