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
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c0e849d1fee7eca67f3b5765d31b54e0660eaa25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
|[Mutex::Mutex Oluşturucusu](../windows/mutex-mutex-constructor.md)|Mutex sınıfı yeni bir örneğini başlatır.|  
  
### <a name="public-members"></a>Genel üyeler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Mutex::Lock Metodu](../windows/mutex-lock-method.md)|Geçerli nesne ya da belirtilen tanıtıcı ile ilişkili Mutex nesne kadar bekler yayımları mutex veya belirtilen zaman aşımı aralığı geçti.|  
  
### <a name="public-operator"></a>Genel işleç  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Mutex::operator= İşleci](../windows/mutex-operator-assign-operator.md)|Atar (taşır) belirtilen Mutex geçerli Mutex nesnesi nesne.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Mutex`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)