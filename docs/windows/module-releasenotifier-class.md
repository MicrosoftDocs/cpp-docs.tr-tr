---
title: Module::ReleaseNotifier sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- ReleaseNotifier class
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1deeb3076d3f1bfc2243ec333f258f543a37fceb
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608397"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier Sınıfı
Modül içindeki son nesnenin yayımlandığında bir olay işleyici çağırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class ReleaseNotifier;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::ReleaseNotifier::~ReleaseNotifier Yıkıcısı](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|Geçerli örneğinin başlatmasını geri alır **Module::ReleaseNotifier** sınıfı.|  
|[Module::ReleaseNotifier::ReleaseNotifier Oluşturucusu](../windows/module-releasenotifier-releasenotifier-constructor.md)|Yeni bir örneğini başlatır **Module::ReleaseNotifier** sınıfı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::ReleaseNotifier::Invoke Metodu](../windows/module-releasenotifier-invoke-method.md)|Modül içindeki son nesnenin serbest bırakıldığında uygulandığında, bir olay işleyici çağırır.|  
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|Geçerli siler **Module::ReleaseNotifier** nesnesi bir parametre ile oluşturulmuş nesne **true**.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ReleaseNotifier`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül Sınıfı](../windows/module-class.md)