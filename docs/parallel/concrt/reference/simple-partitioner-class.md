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
ms.openlocfilehash: a9e4526f86423d1b374bf08a6837e47afb884960
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Eşzamanlılık Namespace](concurrency-namespace.md)
