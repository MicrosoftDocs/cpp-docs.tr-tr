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
ms.openlocfilehash: 9e850c90ef873e64352ace64ff680cd93474a4a1
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606429"
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier Sınıfı
Geçerli modül içinde son nesnenin yayımlandığında bir olay işleyici çağırır. Olay işleyici lambda, functor veya işaretçi işlevi tarafından belirtilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename T>  
class GenericReleaseNotifier : public ReleaseNotifier;  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Olay işleyicisi konumunu içeren veri üye türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::GenericReleaseNotifier Oluşturucusu](../windows/module-genericreleasenotifier-genericreleasenotifier-constructor.md)|Yeni bir örneğini başlatır **Module::GenericReleaseNotifier** sınıfı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::Invoke Metodu](../windows/module-genericreleasenotifier-invoke-method.md)|Geçerli ile ilişkili olay işleyicisini çağırır **Module::GenericReleaseNotifier** nesne.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::callback_ Veri Üyesi](../windows/module-genericreleasenotifier-callback-data-member.md)|Lambda, functor ya da işaretçi işlevi olay işleyicisi geçerli ilişkili **Module::GenericReleaseNotifier** nesne.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ReleaseNotifier`  
  
 `GenericReleaseNotifier`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül Sınıfı](../windows/module-class.md)