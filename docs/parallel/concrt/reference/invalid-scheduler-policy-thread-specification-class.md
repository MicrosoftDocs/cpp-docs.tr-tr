---
title: invalid_scheduler_policy_thread_specification sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_thread_specification
dev_langs:
- C++
helpviewer_keywords:
- invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53e2d5ba1c8fd4d8afd4af88c45069b34717a66c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="invalidschedulerpolicythreadspecification-class"></a>invalid_scheduler_policy_thread_specification Sınıfı
Bu sınıf eşzamanlılık sınırlarını ayarlamak için bir girişimde zaman oluşturulan bir özel açıklar bir `SchedulerPolicy` nesne şekilde değerini `MinConcurrency` anahtar değerini azdır `MaxConcurrency` anahtarı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class invalid_scheduler_policy_thread_specification : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[invalid_scheduler_policy_thread_specification] (geçersiz-Zamanlayıcı-ilke-değer-class.md #ctor|Fazla Yüklendi. Oluşturan bir `invalid_scheduler_policy_value` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `invalid_scheduler_policy_thread_specification`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
##  <a name="ctor"></a> invalid_scheduler_policy_thread_specification 

 Oluşturan bir `invalid_scheduler_policy_value` nesnesi.  
  
```
explicit _CRTIMP invalid_scheduler_policy_thread_specification(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_thread_specification() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hata açıklayıcı bir ileti.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [SchedulerPolicy Sınıfı](schedulerpolicy-class.md)
