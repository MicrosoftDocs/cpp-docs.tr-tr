---
title: improper_lock sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- improper_lock
- CONCRT/concurrency::improper_lock
- CONCRT/concurrency::improper_lock::improper_lock
dev_langs:
- C++
helpviewer_keywords:
- improper_lock class
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 19a4a150b2cdf067802a1220a77640f20a1fea51
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106200"
---
# <a name="improperlock-class"></a>improper_lock Sınıfı
Bu sınıf, bir kilit alınmadığı yanlış olduğunda oluşturulan bir özel durum açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class improper_lock : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[improper_lock](#ctor)|Fazla Yüklendi. Oluşturur bir `improper_lock exception`.|  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle, bir reentrant olmayan kilit yinelemeli olarak aynı içerik üzerinde almaya denemesi yapıldığında bu özel durum oluşturulur.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `improper_lock`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a> improper_lock 

 Oluşturur bir `improper_lock exception`.  
  
```
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```  
  
### <a name="parameters"></a>Parametreler  
*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [critical_section sınıfı](critical-section-class.md)   
 [reader_writer_lock Sınıfı](reader-writer-lock-class.md)
