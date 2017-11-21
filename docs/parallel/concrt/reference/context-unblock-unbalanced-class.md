---
title: "context_unblock_unbalanced sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
dev_langs: C++
helpviewer_keywords: context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 45121b3dba14e5672333debf364f5aea2e3e3cd5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="contextunblockunbalanced-class"></a>context_unblock_unbalanced Sınıfı
Bu sınıf ne zaman oluşturulan bir özel tanımlar çağrılar `Block` ve `Unblock` yöntemlerinin bir `Context` nesne değil düzgün eşlenmemiş.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class context_unblock_unbalanced : public std::exception;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[context_unblock_unbalanced](#ctor)|Fazla Yüklendi. Oluşturan bir `context_unblock_unbalanced` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrılar `Block` ve `Unblock` yöntemlerinin bir `Context` nesne her zaman doğru eşleştirilmelidir. Eşzamanlılık Çalışma zamanı ya da sırada olmasını işlemlere izin verir. Örneğin, bir çağrı `Block` için yapılan bir çağrı tarafından izlenen `Unblock`, ya da tam tersini. Örneğin, iki için çağrılar içeriyorsa, bu özel durum `Unblock` yöntemi, üzerinde bir satırda yapıldı bir `Context` değil engellenmiş olan bir nesne.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `context_unblock_unbalanced`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a>context_unblock_unbalanced 

 Oluşturan bir `context_unblock_unbalanced` nesnesi.  
  
```  
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

 
context_unblock_unbalanced() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hata açıklayıcı bir ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)
