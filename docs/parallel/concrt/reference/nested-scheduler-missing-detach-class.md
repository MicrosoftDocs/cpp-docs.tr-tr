---
title: nested_scheduler_missing_detach sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach
dev_langs:
- C++
helpviewer_keywords:
- nested_scheduler_missing_detach class
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 26027693209bc5b4687686efeae5d190ed374607
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="nestedschedulermissingdetach-class"></a>nested_scheduler_missing_detach Sınıfı
Bu sınıf eşzamanlılık çalışma zamanı çağırmak ihmal algıladığında oluşturulan bir özel tanımlar `CurrentScheduler::Detach` yöntemi kullanarak ikinci bir zamanlayıcı bağlı bir bağlamda `Attach` yöntemi `Scheduler` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class nested_scheduler_missing_detach : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[nested_scheduler_missing_detach](#ctor)|Fazla Yüklendi. Oluşturan bir `nested_scheduler_missing_detach` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Çağırarak bir zamanlayıcı iç içe olduğunda bu durum `Attach` yöntemi bir `Scheduler` zaten sahip olduğu veya başka bir zamanlayıcı bağlı bir'context nesnesinde. Senaryo sorunu bulmak için bir yardımcı olarak algılayabildiği zaman eşzamanlılık çalışma zamanı bu özel durum mümkün oluşturur. Her örneğini çağrı ihmal `CurrentScheduler::Detach` yöntemi, bu özel durum için garanti.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `nested_scheduler_missing_detach`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a> nested_scheduler_missing_detach 

 Oluşturan bir `nested_scheduler_missing_detach` nesnesi.  
  
```
explicit _CRTIMP nested_scheduler_missing_detach(_In_z_ const char* _Message) throw();

nested_scheduler_missing_detach() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hata açıklayıcı bir ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Zamanlayıcı Sınıfı](scheduler-class.md)
