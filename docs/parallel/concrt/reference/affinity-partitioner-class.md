---
title: "affinity_partitioner sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- affinity_partitioner
- PPL/concurrency::affinity_partitioner
- PPL/concurrency::affinity_partitioner::affinity_partitioner
dev_langs: C++
helpviewer_keywords: affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 25d6edb53a291c7b3a86f8583b78ab3efdce7842
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="affinitypartitioner-class"></a>affinity_partitioner Sınıfı
`affinity_partitioner` Sınıfı benzer `static_partitioner` sınıfı, ancak çalışan iş parçacığı alt aralıklara eşleme dilediği tarafından önbellek benzeşim artırır. Döngü aynı veri kümesi üzerinde yeniden yürütülen olduğunda ve veri önbelleği'nde uygun, performansı önemli ölçüde artırabilir. Unutmayın aynı `affinity_partitioner` nesnesi belirli veri veri yerleşim yararlanmak için küme üzerinde yürütülen paralel bir döngüden sonraki yinelemelerini kullanılmalıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class affinity_partitioner;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[affinity_partitioner](#ctor)|Oluşturan bir `affinity_partitioner` nesnesi.|  
|[~ affinity_partitioner yok Edicisi](#dtor)|Bozar bir `affinity_partitioner` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `affinity_partitioner`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ppl.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="dtor"></a>~ affinity_partitioner 

 Bozar bir `affinity_partitioner` nesnesi.  
  
```
~affinity_partitioner();
```  
  
##  <a name="ctor"></a>affinity_partitioner 

 Oluşturan bir `affinity_partitioner` nesnesi.  
  
```
affinity_partitioner();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
