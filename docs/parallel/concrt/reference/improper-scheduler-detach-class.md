---
title: improper_scheduler_detach sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach::improper_scheduler_detach
dev_langs:
- C++
helpviewer_keywords:
- improper_scheduler_detach class
ms.assetid: 30132102-c900-4951-a470-b63b4e3aa2d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd492f28f2aba76e9d6e6d3b381d4d0de4c30202
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059213"
---
# <a name="improperschedulerdetach-class"></a>improper_scheduler_detach Sınıfı
Bu sınıf oluşan bir özel durumu anlatmaktadır `CurrentScheduler::Detach` yöntemi kullanarak herhangi bir zamanlayıcı için bağlı olmayan bir bağlamı çağrıldığında `Attach` yöntemi bir `Scheduler` nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class improper_scheduler_detach : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[improper_scheduler_detach](#ctor)|Fazla Yüklendi. Oluşturur bir `improper_scheduler_detach` nesne.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `improper_scheduler_detach`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a> improper_scheduler_detach 

 Oluşturur bir `improper_scheduler_detach` nesne.  
  
```
explicit _CRTIMP improper_scheduler_detach(_In_z_ const char* _Message) throw();

improper_scheduler_detach() throw();
```  
  
### <a name="parameters"></a>Parametreler  
*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Zamanlayıcı Sınıfı](scheduler-class.md)
