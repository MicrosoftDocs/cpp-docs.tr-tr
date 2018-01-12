---
title: "invalid_compute_domain sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- invalid_compute_domain
- AMPRT/invalid_compute_domain
- AMPRT/Concurrency::invalid_compute_domain::invalid_compute_domain
dev_langs: C++
helpviewer_keywords: invalid_compute_domain class
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9dc142b921efb6b52fd5b5ce7a89432b4727951c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="invalidcomputedomain-class"></a>invalid_compute_domain Sınıfı
Çalışma zamanı sırasında belirtilen işlem etki alanı kullanarak bir çekirdek başlatılamıyor olmadığında oluşan özel durum [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each) çağrısı site.  

  
## <a name="syntax"></a>Sözdizimi  
  
```  
class invalid_compute_domain : public runtime_exception;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[invalid_compute_domain Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `invalid_compute_domain` sınıfı.|  

  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `runtime_exception`  
  
 `invalid_compute_domain`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amprt.h  
  
 **Namespace:** eşzamanlılık  

## <a name="ctor"></a>invalid_compute_domain 

Sınıfının yeni bir örneğini başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
explicit invalid_compute_domain(  
    const char * _Message ) throw();  
  
invalid_compute_domain() throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hatanın açıklaması.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Örneği `invalid_compute_domain` sınıfı  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
