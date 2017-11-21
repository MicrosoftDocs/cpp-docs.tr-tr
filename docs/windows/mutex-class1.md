---
title: Mutex Class1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Mutex
dev_langs: C++
helpviewer_keywords: Mutex class
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b3f0295ce9456822337c9beac3e6d1c35f7d80bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mutex-class1"></a>Mutex Class1
Paylaşılan bir kaynak yalnızca denetleyen eşitleme nesnesi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class Mutex : public HandleT<HandleTraits::MutexTraits>  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|**SyncLock**|Zaman uyumlu kilitleri destekleyen bir sınıf eşanlamlısı.|  
  
### <a name="public-constructor"></a>Genel oluşturucu  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Mutex::mutex Oluşturucusu](../windows/mutex-mutex-constructor.md)|Mutex sınıfı yeni bir örneğini başlatır.|  
  
### <a name="public-members"></a>Genel üyeler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Mutex::Lock yöntemi](../windows/mutex-lock-method.md)|Geçerli nesne ya da belirtilen tanıtıcı ile ilişkili Mutex nesne kadar bekler yayımları mutex veya belirtilen zaman aşımı aralığı geçti.|  
  
### <a name="public-operator"></a>Genel işleç  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Mutex::operator = işleci](../windows/mutex-operator-assign-operator.md)|Atar (taşır) belirtilen Mutex geçerli Mutex nesnesi nesne.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Mutex`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: Wrappers Namespace](../windows/microsoft-wrl-wrappers-namespace.md)