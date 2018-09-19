---
title: uninitialized_object sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- uninitialized_object
- AMPRT/uninitialized_object
- AMPRT/Concurrency::uninitialized_object
dev_langs:
- C++
helpviewer_keywords:
- uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 821f3c25d195a2c92ac04fdf5f9e5a59b493c257
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113844"
---
# <a name="uninitializedobject-class"></a>uninitialized_object Sınıfı
Başlatılmamış bir nesne kullanıldığında oluşturulan özel durum.  
  
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
## <a name="uninitialized_object__ctor"></a> unsupported_feature 

Unsupported_feature özel durumunun yeni bir örneğini oluşturur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
explicit unsupported_feature(  
    const char * _Message ) throw();  
  
unsupported_feature() throw();  
```  
  
### <a name="parameters"></a>Parametreler  
*İl_eti*<br/>
Hatanın açıklaması.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `unsupported_feature` Nesne. 

## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
