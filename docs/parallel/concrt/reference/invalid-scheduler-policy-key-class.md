---
title: "invalid_scheduler_policy_key sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key::invalid_scheduler_policy_key
dev_langs: C++
helpviewer_keywords: invalid_scheduler_policy_key class
ms.assetid: 6a7c42fe-9bc4-4a02-bebb-99fe9ef9817d
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8de8f3a9a027a1b9ae4862d21e27a45f110047b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="invalidschedulerpolicykey-class"></a>invalid_scheduler_policy_key Sınıfı
Bu sınıf geçersiz bir zaman oluşturulan bir özel tanımlar veya Bilinmeyen anahtar için geçirilen bir `SchedulerPolicy` Nesne oluşturucusu veya `SetPolicyValue` yöntemi bir `SchedulerPolicy` nesnesi gibi başka yöntemler kullanılarak değiştirilmelidir bir anahtar geçirildi `SetConcurrencyLimits` yöntemi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class invalid_scheduler_policy_key : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[invalid_scheduler_policy_key](#ctor)|Fazla Yüklendi. Oluşturan bir `invalid_scheduler_policy_key` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `invalid_scheduler_policy_key`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a>invalid_scheduler_policy_key 

 Oluşturan bir `invalid_scheduler_policy_key` nesnesi.  
  
```
explicit _CRTIMP invalid_scheduler_policy_key(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_key() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hata açıklayıcı bir ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [SchedulerPolicy Sınıfı](schedulerpolicy-class.md)
