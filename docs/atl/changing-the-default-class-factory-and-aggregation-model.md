---
title: "Varsayılan üreteci ve toplama modeli değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a963c1fba2d3eda9c86fa1e6db74de739bf45182
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="changing-the-default-class-factory-and-aggregation-model"></a>Varsayılan üreteci ve toplama modelini değiştirme
ATL kullanan [CComCoClass](../atl/reference/ccomcoclass-class.md) , nesne için varsayılan sınıf Fabrika ve toplama modeli tanımlamak için. `CComCoClass`Aşağıdaki iki makroları belirtir:  
  
-   [DECLARE_CLASSFACTORY](reference/aggregation-and-class-factory-macros.md#declare_classfactory) olmasını üreteci bildirir [CComClassFactory](../atl/reference/ccomclassfactory-class.md).  
  
-   [DECLARE_AGGREGATABLE](reference/aggregation-and-class-factory-macros.md#declare_aggregatable) nesnenizin kümelenebilir bildirir.  
  
 Bu varsayılan birini Sınıf tanımınız içinde başka bir makrosu belirterek geçersiz kılabilirsiniz. Örneğin, kullanılacak [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) yerine `CComClassFactory`, belirtin [DECLARE_CLASSFACTORY2](reference/aggregation-and-class-factory-macros.md#declare_classfactory2) makrosu:  
  
 [!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/cpp/changing-the-default-class-factory-and-aggregation-model_1.h)]  
  
 Bir sınıf fabrikası tanımlayın iki makroların [DECLARE_CLASSFACTORY_AUTO_THREAD](reference/aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) ve [DECLARE_CLASSFACTORY_SINGLETON](reference/aggregation-and-class-factory-macros.md#declare_classfactory_singleton).  
  
 ATL de kullanır `typedef` varsayılan davranışı uygulamak için bir mekanizma. Örneğin, `DECLARE_AGGREGATABLE` makrosu kullanan `typedef` adlı tür tanımlamak için **_CreatorClass**, hangi sonra başvurulmaktadır ATL Türetilen bir sınıfta unutmayın bir `typedef` temel sınıfın aynı adı kullanarak `typedef` tanımınızı kullanarak ve varsayılan davranışı geçersiz kılma ATL neden olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM nesneleri temelleri](../atl/fundamentals-of-atl-com-objects.md)   
 [Toplama ve sınıf Fabrika makroları](../atl/reference/aggregation-and-class-factory-macros.md)

