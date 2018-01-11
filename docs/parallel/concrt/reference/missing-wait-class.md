---
title: "missing_wait sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
dev_langs: C++
helpviewer_keywords: missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 952a2b88ebb91449341085a923e06d389aa10fe4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="missingwait-class"></a>missing_wait Sınıfı
Bu sınıf için hala zamanlanmış görevler olduğunda oluşturulan bir özel açıklayan bir `task_group` veya `structured_task_group` aynı anda bu nesnenin nesne yıkıcı yürütür. Yıkıcı bir özel durum sonucu olarak geriye doğru izleme yığını nedeniyle ulaşıldığında bu özel durumun hiçbir zaman oluşturulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class missing_wait : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[missing_wait](#ctor)|Fazla Yüklendi. Oluşturan bir `missing_wait` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Özel durum akış ya da çağırmak için sorumlu `wait` veya `run_and_wait` yöntemi bir `task_group` veya `structured_task_group` destruct söz konusu nesne izin vermeden önce nesnesi. Çalışma zamanı bu özel durum çağrı unuttunuz bir göstergesi olarak atar `wait` veya `run_and_wait` yöntemi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `missing_wait`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a>missing_wait 

 Oluşturan bir `missing_wait` nesnesi.  
  
```
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hata açıklayıcı bir ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [task_group sınıfı](task-group-class.md)   
 [bekleme](task-group-class.md)   
 [run_and_wait](task-group-class.md)   
 [structured_task_group Sınıfı](structured-task-group-class.md)
