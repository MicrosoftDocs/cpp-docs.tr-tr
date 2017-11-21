---
title: "auto_partitioner sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- auto_partitioner
- PPL/concurrency::auto_partitioner
- PPL/concurrency::auto_partitioner::auto_partitioner
dev_langs: C++
helpviewer_keywords: auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 81886c605c012f54377f1dbf356873000dc3359a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="autopartitioner-class"></a>auto_partitioner Sınıfı
`auto_partitioner` Sınıfı temsil eder, varsayılan yöntemi `parallel_for`, `parallel_for_each` ve `parallel_transform` tekrarlanan üzerinden aralığı bölüm için kullanın. Employes bölümlendirme, bu yöntem Yük Dengeleme için çalarak aralığı yanı sıra başına-iptal yineleme.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class auto_partitioner;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[auto_partitioner](#ctor)|Oluşturan bir `auto_partitioner` nesnesi.|  
|[~ auto_partitioner yok Edicisi](#dtor)|Bozar bir `auto_partitioner` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `auto_partitioner`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ppl.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="dtor"></a>~ auto_partitioner 

 Bozar bir `auto_partitioner` nesnesi.  
  
```
~auto_partitioner();
```  
  
##  <a name="ctor"></a>auto_partitioner 

 Oluşturan bir `auto_partitioner` nesnesi.  
  
```
auto_partitioner();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)
