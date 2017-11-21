---
title: "improper_scheduler_reference sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference::improper_scheduler_reference
dev_langs: C++
helpviewer_keywords: improper_scheduler_reference class
ms.assetid: 434a7512-7796-4255-92a7-f3bf71c6a7a7
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 367f939145b0fa716d2d975b7bf2315594a760a1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="improperschedulerreference-class"></a>improper_scheduler_reference Sınıfı
Bu sınıf ne zaman oluşturulan bir özel tanımlar `Reference` yöntemi çağrıldığında bir `Scheduler` aşağı, bu Zamanlayıcı parçası olmayan bir bağlamından kapatılıyor nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class improper_scheduler_reference : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[improper_scheduler_reference](#ctor)|Fazla Yüklendi. Oluşturan bir `improper_scheduler_reference` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `improper_scheduler_reference`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a>improper_scheduler_reference 

 Oluşturan bir `improper_scheduler_reference` nesnesi.  
  
```
explicit _CRTIMP improper_scheduler_reference(_In_z_ const char* _Message) throw();

improper_scheduler_reference() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hata açıklayıcı bir ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Zamanlayıcı sınıfı](scheduler-class.md)
