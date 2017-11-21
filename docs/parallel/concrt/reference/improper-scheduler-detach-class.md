---
title: "improper_scheduler_detach sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach::improper_scheduler_detach
dev_langs: C++
helpviewer_keywords: improper_scheduler_detach class
ms.assetid: 30132102-c900-4951-a470-b63b4e3aa2d2
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 81d4f0169c598c9321166ae952e1f594202781d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="improperschedulerdetach-class"></a>improper_scheduler_detach Sınıfı
Bu sınıf ne zaman oluşturulan bir özel tanımlar `CurrentScheduler::Detach` yöntemi kullanarak tüm Zamanlayıcı bağlı olmayan bir bağlamda çağrılır `Attach` yöntemi bir `Scheduler` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class improper_scheduler_detach : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[improper_scheduler_detach](#ctor)|Fazla Yüklendi. Oluşturan bir `improper_scheduler_detach` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `improper_scheduler_detach`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a>improper_scheduler_detach 

 Oluşturan bir `improper_scheduler_detach` nesnesi.  
  
```
explicit _CRTIMP improper_scheduler_detach(_In_z_ const char* _Message) throw();

improper_scheduler_detach() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hata açıklayıcı bir ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Zamanlayıcı sınıfı](scheduler-class.md)
