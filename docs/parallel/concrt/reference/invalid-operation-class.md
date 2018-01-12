---
title: "invalid_operation sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- invalid_operation
- CONCRT/concurrency::invalid_operation
- CONCRT/concurrency::invalid_operation::invalid_operation
dev_langs: C++
helpviewer_keywords: invalid_operation class
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 67bd4819f3f1820ae9a13cc07fc2db692a362433
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="invalidoperation-class"></a>invalid_operation Sınıfı
Bu sınıf daha doğru bir şekilde eşzamanlılık çalışma zamanı tarafından oluşturulan başka bir özel durum türü tarafından açıklanmayan geçersiz bir işlem gerçekleştirilirken oluşturulan bir özel açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class invalid_operation : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[invalid_operation](#ctor)|Fazla Yüklendi. Oluşturan bir `invalid_operation` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu özel durum çeşitli yöntemleri, genellikle hangi durumlarda bunlar, özel durum oluşturacak altında belge.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `invalid_operation`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a>invalid_operation 

 Oluşturan bir `invalid_operation` nesnesi.  
  
```
explicit _CRTIMP invalid_operation(_In_z_ const char* _Message) throw();

invalid_operation() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hata açıklayıcı bir ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
