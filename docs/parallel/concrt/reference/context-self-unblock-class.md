---
title: "context_self_unblock sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- context_self_unblock
- CONCRT/concurrency::context_self_unblock
- CONCRT/concurrency::context_self_unblock::context_self_unblock
dev_langs: C++
helpviewer_keywords: context_self_unblock class
ms.assetid: 9601cd28-4f40-4c2e-89ab-747068956331
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0478e018aadd0e8e73da3691d2b9bf6974569f23
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="contextselfunblock-class"></a>context_self_unblock Sınıfı
Bu sınıf ne zaman oluşturulan bir özel tanımlar `Unblock` yöntemi bir `Context` nesnesi aynı bağlamdan çağrılır. Bu girişiminde tarafından belirli bir bağlam kendisini engellemesini kaldırmak için gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class context_self_unblock : public std::exception;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[context_self_unblock](#ctor)|Fazla Yüklendi. Oluşturan bir `context_self_unblock` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `context_self_unblock`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a>context_self_unblock 

 Oluşturan bir `context_self_unblock` nesnesi.  
  
```  
explicit _CRTIMP context_self_unblock(_In_z_ const char* _Message) throw();

 
context_self_unblock() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hata açıklayıcı bir ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
