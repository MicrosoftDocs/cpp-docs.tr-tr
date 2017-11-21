---
title: "invalid_multiple_scheduling sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling::invalid_multiple_scheduling
dev_langs: C++
helpviewer_keywords: invalid_multiple_scheduling class
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 86d2680234b1d6f957e9f19f9cacc372f7fc8eff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="invalidmultiplescheduling-class"></a>invalid_multiple_scheduling Sınıfı
Bu sınıf ne zaman oluşturulan bir özel tanımlar bir `task_handle` nesnesidir zamanlanmış birden çok kez kullanarak `run` yöntemi bir `task_group` veya `structured_task_group` nesne ya da müdahalede bulunan bir çağrı olmadan `wait` veya `run_and_wait` yöntemleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class invalid_multiple_scheduling : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[invalid_multiple_scheduling](#ctor)|Fazla Yüklendi. Oluşturan bir `invalid_multiple_scheduling` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `invalid_multiple_scheduling`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a>invalid_multiple_scheduling 

 Oluşturan bir `invalid_multiple_scheduling` nesnesi.  
  
```
explicit _CRTIMP invalid_multiple_scheduling(_In_z_ const char* _Message) throw();

invalid_multiple_scheduling() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hata açıklayıcı bir ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [task_handle sınıfı](task-handle-class.md)   
 [task_group sınıfı](task-group-class.md)   
 [çalıştırma](task-group-class.md)   
 [bekleme](task-group-class.md)   
 [run_and_wait](task-group-class.md)   
 [structured_task_group sınıfı](structured-task-group-class.md)
