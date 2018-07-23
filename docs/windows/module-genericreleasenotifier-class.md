---
title: Module::GenericReleaseNotifier sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- GenericReleaseNotifier class
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c3ba58e08bac36d905fbf874546d7791f2aa3fcb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882014"
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier Sınıfı
Son nesne geçerli modülünde yayımlandığında, bir olay işleyiciyi çağırır. Olay işleyicisi lambda, functor veya işaretçi işlevi belirtilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename T>  
class GenericReleaseNotifier : public ReleaseNotifier;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Olay işleyicisi konumunu içeren veri üyesi türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::GenericReleaseNotifier Oluşturucusu](../windows/module-genericreleasenotifier-genericreleasenotifier-constructor.md)|Module::GenericReleaseNotifier sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::Invoke Metodu](../windows/module-genericreleasenotifier-invoke-method.md)|Geçerli Module::GenericReleaseNotifier nesneyle ilişkili olay işleyicisini çağırır.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::callback_ Veri Üyesi](../windows/module-genericreleasenotifier-callback-data-member.md)|Lambda, functor ya da geçerli Module::GenericReleaseNotifier nesneyle ilişkili işaretçi işlevi olay işleyicisi barındırır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ReleaseNotifier`  
  
 `GenericReleaseNotifier`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül Sınıfı](../windows/module-class.md)