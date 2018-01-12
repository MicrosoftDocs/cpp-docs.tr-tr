---
title: "uninitialized_object sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- uninitialized_object
- AMPRT/uninitialized_object
- AMPRT/Concurrency::uninitialized_object
dev_langs: C++
helpviewer_keywords: uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 75d3050c128b067833352ea82aee38bcd2a7019d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="uninitializedobject-class"></a>uninitialized_object Sınıfı
Başlatılmamış bir nesneye kullanıldığında oluşan özel durum.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class uninitialized_object : public runtime_exception;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[uninitialized_object Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `uninitialized_object` sınıfı.|  

  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `runtime_exception`  
  
 `uninitialized_object`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amprt.h  
  
 **Namespace:** eşzamanlılık  
## <a name="uninitialized_object__ctor"></a>unsupported_feature 

Unsupported_feature özel durum yeni bir örneğini oluşturur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
explicit unsupported_feature(  
    const char * _Message ) throw();  
  
unsupported_feature() throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hatanın açıklaması.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `unsupported_feature` Nesnesi. 

## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
