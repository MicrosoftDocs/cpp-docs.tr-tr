---
title: "static_partitioner sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
dev_langs: C++
helpviewer_keywords: static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 110091a414f9cfeebcdf236b7eed6a9e46e06ea2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="staticpartitioner-class"></a>static_partitioner Sınıfı
`static_partitioner` Sınıfı temsil eden bir statik üzerinden tarafından yinelendiğinde aralığının bölümleme `parallel_for`. Bölümleyici aralığı çalışanları underyling Zamanlayıcı kullanılabilir olduğu kadar parçalara ayırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class static_partitioner;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[static_partitioner](#ctor)|Oluşturan bir `static_partitioner` nesnesi.|  
|[~ static_partitioner yok Edicisi](#dtor)|Bozar bir `static_partitioner` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `static_partitioner`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ppl.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="dtor"></a>~ static_partitioner 

 Bozar bir `static_partitioner` nesnesi.  
  
```
~static_partitioner();
```  
  
##  <a name="ctor"></a>static_partitioner 

 Oluşturan bir `static_partitioner` nesnesi.  
  
```
static_partitioner();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)
