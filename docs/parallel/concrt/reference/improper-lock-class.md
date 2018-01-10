---
title: "improper_lock sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- improper_lock
- CONCRT/concurrency::improper_lock
- CONCRT/concurrency::improper_lock::improper_lock
dev_langs: C++
helpviewer_keywords: improper_lock class
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 876023cbc559364a51f7c0774b7b5d04a11a65d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="improperlock-class"></a>improper_lock Sınıfı
Bu sınıf bir kilit yanlış alındığında bir özel durum açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class improper_lock : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[improper_lock](#ctor)|Fazla Yüklendi. Oluşturan bir `improper_lock exception`.|  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle, yeniden girme olmayan kilit yinelemeli olarak aynı bağlamda edinmeye girişiminde bulunulduğunda bu özel durum oluşur.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `improper_lock`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a>improper_lock 

 Oluşturan bir `improper_lock exception`.  
  
```
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hata açıklayıcı bir ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [critical_section sınıfı](critical-section-class.md)   
 [reader_writer_lock Sınıfı](reader-writer-lock-class.md)
