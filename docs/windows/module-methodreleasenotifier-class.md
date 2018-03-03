---
title: "Module::MethodReleaseNotifier sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- MethodReleaseNotifier class
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 113ea9179292606461a8fe67ff161f63e58161da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier Sınıfı
Son nesne geçerli modülünde yayımlandığında, bir olay işleyiciyi çağırır. Olay işleyicisi bir nesne ve kendi yöntemi için işaretçi üyesi tarafından belirtilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   typename T  
>  
class MethodReleaseNotifier : public ReleaseNotifier;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Olay işleyicisi, üye işlevi olan nesnenin türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::MethodReleaseNotifier Oluşturucusu](../windows/module-methodreleasenotifier-methodreleasenotifier-constructor.md)|Module::MethodReleaseNotifier sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::Invoke Metodu](../windows/module-methodreleasenotifier-invoke-method.md)|Geçerli Module::MethodReleaseNotifier nesneyle ilişkili olay işleyicisini çağırır.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::method_ Veri Üyesi](../windows/module-methodreleasenotifier-method-data-member.md)|Geçerli Module::MethodReleaseNotifier nesnesi için olay işleyicisi için bir işaretçi tutar.|  
|[Module::MethodReleaseNotifier::object_ Veri Üyesi](../windows/module-methodreleasenotifier-object-data-member.md)|Geçerli Module::MethodReleaseNotifier nesnesi için olay işleyicisini, üye işlevi olan nesne için bir işaretçi tutar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ReleaseNotifier`  
  
 `MethodReleaseNotifier`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül Sınıfı](../windows/module-class.md)