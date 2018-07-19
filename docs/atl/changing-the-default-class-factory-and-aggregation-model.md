---
title: Varsayılan sınıf üreteci ve toplama modelini değiştirme | Microsoft Docs
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
ms.openlocfilehash: db2e684565589eb736b135db3460ed8b83d382b1
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850884"
---
# <a name="changing-the-default-class-factory-and-aggregation-model"></a>Varsayılan sınıf üreteci ve toplama modelini değiştirme
ATL kullanan [CComCoClass](../atl/reference/ccomcoclass-class.md) nesneniz için varsayılan sınıf üreteci ve toplama modelini tanımlamak için. `CComCoClass` Aşağıdaki iki makro belirtir:  
  
-   [DECLARE_CLASSFACTORY](reference/aggregation-and-class-factory-macros.md#declare_classfactory) olmasını sınıf üreteci bildirir [CComClassFactory](../atl/reference/ccomclassfactory-class.md).  
  
-   [DECLARE_AGGREGATABLE](reference/aggregation-and-class-factory-macros.md#declare_aggregatable) nesnenizin toplanabilir bildirir.  
  
 Başka bir makro, sınıf tanımında belirterek ya da bu varsayılan geçersiz kılabilirsiniz. Örneğin, kullanılacak [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) yerine `CComClassFactory`, belirtin [DECLARE_CLASSFACTORY2](reference/aggregation-and-class-factory-macros.md#declare_classfactory2) makrosu:  
  
 [!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/cpp/changing-the-default-class-factory-and-aggregation-model_1.h)]  
  
 Bir sınıf üreteci tanımlayan iki diğer makroların [DECLARE_CLASSFACTORY_AUTO_THREAD](reference/aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) ve [DECLARE_CLASSFACTORY_SINGLETON](reference/aggregation-and-class-factory-macros.md#declare_classfactory_singleton).  
  
 ATL ayrıca kullanan **typedef** varsayılan davranışı uygulamak mekanizması. Örneğin, DECLARE_AGGREGATABLE makro kullanır **typedef** adlı bir tür tanımlamak için `_CreatorClass`, hangi ardından başvuruluyor ATL Türetilen bir sınıfta unutmayın bir **typedef** temel sınıfın aynı adı kullanarak **typedef** tanımınızı kullanan ve varsayılan davranışı geçersiz kılma ATL sonuçlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM nesnelerinin temelleri](../atl/fundamentals-of-atl-com-objects.md)   
 [Toplama ve Sınıf Üreticisi Makroları](../atl/reference/aggregation-and-class-factory-macros.md)

