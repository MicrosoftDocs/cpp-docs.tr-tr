---
title: missing_wait sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
dev_langs:
- C++
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2a44cbdb5abeed7d5dbd7be7dfaba37ba1d0145
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024963"
---
# <a name="missingwait-class"></a>missing_wait Sınıfı
Bu sınıf için yine de zamanlanmış görevler olduğunda oluşturulan bir özel açıklayan bir `task_group` veya `structured_task_group` sırada bu nesnenin nesne yok Edicisi yürütür. Bu özel durumun hiçbir zaman yok edici bir özel durum sonucu olarak geriye doğru izleme yığın nedeniyle ulaşılırsa oluşturulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class missing_wait : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[missing_wait](#ctor)|Fazla Yüklendi. Oluşturur bir `missing_wait` nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Özel durum akış ya da çağırmak için sorumlu `wait` veya `run_and_wait` yöntemi bir `task_group` veya `structured_task_group` söz konusu nesneyi yok etmek üzere izin vermeden önce nesne. Çalışma zamanı bu Exception'a çağrılacak unuttum bir gösterge olarak `wait` veya `run_and_wait` yöntemi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `missing_wait`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a> missing_wait 

 Oluşturur bir `missing_wait` nesne.  
  
```
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```  
  
### <a name="parameters"></a>Parametreler  
*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [task_group sınıfı](task-group-class.md)   
 [bekleme](task-group-class.md)   
 [run_and_wait](task-group-class.md)   
 [structured_task_group Sınıfı](structured-task-group-class.md)
