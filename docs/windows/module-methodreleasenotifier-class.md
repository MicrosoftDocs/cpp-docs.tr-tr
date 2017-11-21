---
title: "Module::MethodReleaseNotifier sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::MethodReleaseNotifier
dev_langs: C++
helpviewer_keywords: MethodReleaseNotifier class
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 474d4f82b41eaab43c5e87ca335b911db0b4e64e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[Module::methodreleasenotifier:: methodreleasenotifier Oluşturucusu](../windows/module-methodreleasenotifier-methodreleasenotifier-constructor.md)|Module::MethodReleaseNotifier sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier:: Invoke yöntemi](../windows/module-methodreleasenotifier-invoke-method.md)|Geçerli Module::MethodReleaseNotifier nesneyle ilişkili olay işleyicisini çağırır.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::methodreleasenotifier:: method_ veri üyesi](../windows/module-methodreleasenotifier-method-data-member.md)|Geçerli Module::MethodReleaseNotifier nesnesi için olay işleyicisi için bir işaretçi tutar.|  
|[Module::methodreleasenotifier:: object_ veri üyesi](../windows/module-methodreleasenotifier-object-data-member.md)|Geçerli Module::MethodReleaseNotifier nesnesi için olay işleyicisini, üye işlevi olan nesne için bir işaretçi tutar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ReleaseNotifier`  
  
 `MethodReleaseNotifier`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül sınıfı](../windows/module-class.md)