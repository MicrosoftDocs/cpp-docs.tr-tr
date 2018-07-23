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
ms.openlocfilehash: 76edb403fae12dd8b6221d8bd6ec82424bc5a4f7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878398"
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
|[Module::ReleaseNotifier::~ReleaseNotifier Yıkıcısı](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|Module::ReleaseNotifier sınıfının geçerli örneği deinitializes.|  
|[Module::ReleaseNotifier::ReleaseNotifier Oluşturucusu](../windows/module-releasenotifier-releasenotifier-constructor.md)|Module::ReleaseNotifier sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::ReleaseNotifier::Invoke Metodu](../windows/module-releasenotifier-invoke-method.md)|Bir modül son nesnesinde serbest bırakıldığında uygulandığında, olay işleyici çağırır.|  
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|Nesne bir parametre oluşturulan geçerli Module::ReleaseNotifier nesneyi siler `true`.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ReleaseNotifier`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül Sınıfı](../windows/module-class.md)