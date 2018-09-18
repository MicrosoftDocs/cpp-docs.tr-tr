---
title: invalid_multiple_scheduling sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling::invalid_multiple_scheduling
dev_langs:
- C++
helpviewer_keywords:
- invalid_multiple_scheduling class
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3cc4e3b2a23dd5c617b70a7a4b992323a0e963f4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067358"
---
# <a name="invalidmultiplescheduling-class"></a>invalid_multiple_scheduling Sınıfı
Bu sınıf oluşan bir özel durumu anlatmaktadır bir `task_handle` nesnedir kullanarak süreleri zamanlanmış birden çok `run` yöntemi bir `task_group` veya `structured_task_group` nesnesi olmadan bir çağrı göndermelisiniz `wait` veya `run_and_wait` yöntemleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class invalid_multiple_scheduling : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[invalid_multiple_scheduling](#ctor)|Fazla Yüklendi. Oluşturur bir `invalid_multiple_scheduling` nesne.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `invalid_multiple_scheduling`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a> invalid_multiple_scheduling 

 Oluşturur bir `invalid_multiple_scheduling` nesne.  
  
```
explicit _CRTIMP invalid_multiple_scheduling(_In_z_ const char* _Message) throw();

invalid_multiple_scheduling() throw();
```  
  
### <a name="parameters"></a>Parametreler  
*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [task_handle sınıfı](task-handle-class.md)   
 [task_group sınıfı](task-group-class.md)   
 [Çalıştırma](task-group-class.md)   
 [bekleme](task-group-class.md)   
 [run_and_wait](task-group-class.md)   
 [structured_task_group Sınıfı](structured-task-group-class.md)
