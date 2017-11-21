---
title: "Module::ReleaseNotifier sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::ReleaseNotifier
dev_langs: C++
helpviewer_keywords: ReleaseNotifier class
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b48374182d9b39d43cbf0ec99cb51075867e914d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier Sınıfı
Bir modül son nesnesinde yayımlandığında, bir olay işleyiciyi çağırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class ReleaseNotifier;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::ReleaseNotifier:: ~ ReleaseNotifier yok Edicisi](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|Module::ReleaseNotifier sınıfının geçerli örneği deinitializes.|  
|[Module::releasenotifier:: releasenotifier Oluşturucusu](../windows/module-releasenotifier-releasenotifier-constructor.md)|Module::ReleaseNotifier sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::ReleaseNotifier:: Invoke yöntemi](../windows/module-releasenotifier-invoke-method.md)|Bir modül son nesnesinde serbest bırakıldığında uygulandığında, olay işleyici çağırır.|  
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|Nesne bir parametre oluşturulan geçerli Module::ReleaseNotifier nesneyi siler `true`.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ReleaseNotifier`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül sınıfı](../windows/module-class.md)