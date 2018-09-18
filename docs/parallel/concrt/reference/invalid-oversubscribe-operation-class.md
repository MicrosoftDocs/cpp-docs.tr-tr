---
title: invalid_oversubscribe_operation sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation::invalid_oversubscribe_operation
dev_langs:
- C++
helpviewer_keywords:
- invalid_oversubscribe_operation class
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b4e1eaf4bfca27ef22af103a5696ca2a34265d6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069191"
---
# <a name="invalidoversubscribeoperation-class"></a>invalid_oversubscribe_operation Sınıfı
Bu sınıf oluşan bir özel durumu anlatmaktadır `Context::Oversubscribe` yöntemi çağrıldığında `_BeginOversubscription` parametresini `false` çağrıda olmadan `Context::Oversubscribe` yöntemiyle `_BeginOversubscription` parametresini `true`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class invalid_oversubscribe_operation : public std::exception;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[invalid_oversubscribe_operation](#ctor)|Fazla Yüklendi. Oluşturur bir `invalid_oversubscribe_operation` nesne.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `invalid_oversubscribe_operation`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a> invalid_oversubscribe_operation 

 Oluşturur bir `invalid_oversubscribe_operation` nesne.  
  
```  
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

 
invalid_oversubscribe_operation() throw();
```  
  
### <a name="parameters"></a>Parametreler  
*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
