---
title: "Semafor sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Semaphore
dev_langs: C++
helpviewer_keywords: Semaphore class
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 10de04ebed31835d93daca9cf4caa5d96ed605b0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="semaphore-class"></a>Semafor Sınıfı
Kullanıcılar, sınırlı sayıda destekleyebilir paylaşılan bir kaynak denetleyen eşitleme nesnesi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`SyncLock`|Zaman uyumlu kilitleri destekleyen bir sınıf eşanlamlısı.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Semaphore::Semaphore Oluşturucusu](../windows/semaphore-semaphore-constructor.md)|Semafor sınıfı yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Invokehelper::Invoke yöntemi](../windows/invokehelper-invoke-method.md)|Belirtilen bağımsız değişken sayısı, imzası içeren olay işleyicisini çağırır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Semaphore::Lock yöntemi](../windows/semaphore-lock-method.md)|Geçerli nesne ya da belirtilen tanıtıcı ile ilişkili nesne kadar bekler ve iş durumundaki ya da belirtilen zaman aşımı aralığı geçti.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Semaphore::operator = işleci](../windows/semaphore-operator-assign-operator.md)|Belirtilen tanıtıcı geçerli semafor nesnesine bir semafor nesneden taşır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Semaphore`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: Wrappers Namespace](../windows/microsoft-wrl-wrappers-namespace.md)