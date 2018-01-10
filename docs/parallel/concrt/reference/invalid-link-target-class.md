---
title: "invalid_link_target sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- invalid_link_target
- CONCRT/concurrency::invalid_link_target
- CONCRT/concurrency::invalid_link_target::invalid_link_target
dev_langs: C++
helpviewer_keywords: invalid_link_target class
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c428ee5f8b66f09eb9422d3fa76477d77ac08681
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="invalidlinktarget-class"></a>invalid_link_target Sınıfı
Bu sınıf ne zaman oluşturulan bir özel tanımlar `link_target` ileti bloğunun yöntemi çağrılır ve ileti bloğu hedef bağlanamıyor. Bu ileti bloğu izin verilen bağlantı sayısını aşan veya belirli bir hedefe iki kere aynı kaynağına bağlanma girişiminde sonucu olabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class invalid_link_target : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[invalid_link_target](#ctor)|Fazla Yüklendi. Oluşturan bir `invalid_link_target` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `invalid_link_target`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a>invalid_link_target 

 Oluşturan bir `invalid_link_target` nesnesi.  
  
```
explicit _CRTIMP invalid_link_target(_In_z_ const char* _Message) throw();

invalid_link_target() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hata açıklayıcı bir ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Zaman Uyumsuz İleti Blokları](../../../parallel/concrt/asynchronous-message-blocks.md)



