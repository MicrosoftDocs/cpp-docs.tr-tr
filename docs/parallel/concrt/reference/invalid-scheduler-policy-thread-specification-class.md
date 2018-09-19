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
ms.openlocfilehash: ab180a5f52a7645b7ce6cc0f8a04e2ea506f8aa4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016617"
---
# <a name="invalidschedulerpolicythreadspecification-class"></a>invalid_scheduler_policy_thread_specification Sınıfı
Bu sınıf, eşzamanlılık sınırlarını ayarlamak için bir girişimde olduğunda oluşturulan bir özel durum açıklar bir `SchedulerPolicy` nesne gibi değerini `MinConcurrency` anahtar değerini azdır `MaxConcurrency` anahtarı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class invalid_scheduler_policy_thread_specification : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[invalid_scheduler_policy_thread_specification] (geçersiz-Zamanlayıcı-ilkeyi-değeri-class.md #ctor|Fazla Yüklendi. Oluşturur bir `invalid_scheduler_policy_value` nesne.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `invalid_scheduler_policy_thread_specification`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
##  <a name="ctor"></a> invalid_scheduler_policy_thread_specification 

 Oluşturur bir `invalid_scheduler_policy_value` nesne.  
  
```
explicit _CRTIMP invalid_scheduler_policy_thread_specification(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_thread_specification() throw();
```  
  
### <a name="parameters"></a>Parametreler  
*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [SchedulerPolicy Sınıfı](schedulerpolicy-class.md)
