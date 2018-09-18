---
title: context_unblock_unbalanced sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
dev_langs:
- C++
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54911e3e9c696cd2a390dc2f5b42e3917b08014f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037482"
---
# <a name="contextunblockunbalanced-class"></a>context_unblock_unbalanced Sınıfı
Bu sınıf oluşan bir özel durumu anlatmaktadır çağrılar `Block` ve `Unblock` yöntemlerinin bir `Context` nesne değil düzgün halindedir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class context_unblock_unbalanced : public std::exception;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[context_unblock_unbalanced](#ctor)|Fazla Yüklendi. Oluşturur bir `context_unblock_unbalanced` nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrılar `Block` ve `Unblock` yöntemlerinin bir `Context` nesne her zaman doğru eşleştirilmelidir. Eşzamanlılık Çalışma zamanı içinde herhangi bir sırada yapılması işlemlere izin verir. Örneğin, bir çağrı `Block` bir çağrı tarafından izlenebilir `Unblock`, veya tam tersi. Örneğin, iki çağrılar, bu özel durum `Unblock` üzerinde bir satır, metodu yapıldı bir `Context` değil engellendi nesnesidir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `context_unblock_unbalanced`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a> context_unblock_unbalanced 

 Oluşturur bir `context_unblock_unbalanced` nesne.  
  
```  
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

 
context_unblock_unbalanced() throw();
```  
  
### <a name="parameters"></a>Parametreler  
*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
