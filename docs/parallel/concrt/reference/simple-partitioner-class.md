---
title: "simple_partitioner sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
dev_langs: C++
helpviewer_keywords: simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f1d509afd9cddd8ac119d12ce2a0cb88906e83aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="simplepartitioner-class"></a>simple_partitioner Sınıfı
`simple_partitioner` Sınıfı temsil eden bir statik üzerinden tarafından yinelendiğinde aralığının bölümleme `parallel_for`. Her bir öbeğin öbek boyutu tarafından belirtilen yineleme sayısını en az sahip olacağı şekilde bölümleyici aralığı parçalara ayırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class simple_partitioner;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[simple_partitioner](#ctor)|Oluşturan bir `simple_partitioner` nesnesi.|  
|[~ simple_partitioner yok Edicisi](#dtor)|Bozar bir `simple_partitioner` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `simple_partitioner`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ppl.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="dtor"></a>~ simple_partitioner 

 Bozar bir `simple_partitioner` nesnesi.  
  
```
~simple_partitioner();
```  
  
##  <a name="ctor"></a>simple_partitioner 

 Oluşturan bir `simple_partitioner` nesnesi.  
  
```
explicit simple_partitioner(_Size_type _Chunk_size);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Chunk_size`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
