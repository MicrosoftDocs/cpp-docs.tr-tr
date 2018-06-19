---
title: invalid_operation sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- invalid_operation
- CONCRT/concurrency::invalid_operation
- CONCRT/concurrency::invalid_operation::invalid_operation
dev_langs:
- C++
helpviewer_keywords:
- invalid_operation class
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa6d1152bb1f9a9c5671d1f7f0cdf0e426c02575
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33696103"
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
  
##  <a name="ctor"></a> invalid_operation 

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
