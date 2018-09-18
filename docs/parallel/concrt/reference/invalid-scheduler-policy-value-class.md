---
title: invalid_scheduler_policy_value sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_value
dev_langs:
- C++
helpviewer_keywords:
- invalid_scheduler_policy_value class
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae46d9f9de26e80a97d4ea2e9a692caec3445c75
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068162"
---
# <a name="invalidschedulerpolicyvalue-class"></a>invalid_scheduler_policy_value Sınıfı
Bu sınıf bir ilke anahtarı olduğunda oluşturulan bir özel durumu anlatmaktadır bir `SchedulerPolicy` nesne bu anahtar için geçersiz bir değere ayarlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class invalid_scheduler_policy_value : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[invalid_scheduler_policy_value] (invalid-scheduler-policy-thread-specification-class.md#ctor|Fazla Yüklendi. Oluşturur bir `invalid_scheduler_policy_value` nesne.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `invalid_scheduler_policy_value`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
    
##  <a name="ctor"></a> invalid_scheduler_policy_value 

 Oluşturur bir `invalid_scheduler_policy_value` nesne.  
  
```
explicit _CRTIMP invalid_scheduler_policy_value(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_value() throw();
```  
  
### <a name="parameters"></a>Parametreler  
*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.  
  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [SchedulerPolicy Sınıfı](schedulerpolicy-class.md)
