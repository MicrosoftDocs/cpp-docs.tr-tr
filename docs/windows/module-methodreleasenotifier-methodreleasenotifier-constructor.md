---
title: 'Module::methodreleasenotifier:: methodreleasenotifier Oluşturucusu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- MethodReleaseNotifier, constructor
ms.assetid: 762e2ca4-0a92-49de-9ff5-d3efa0f067c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 01c000ee928e9394827a69acb48ef0f41478a699
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018513"
---
# <a name="modulemethodreleasenotifiermethodreleasenotifier-constructor"></a>Module::MethodReleaseNotifier::MethodReleaseNotifier Oluşturucusu
Yeni bir örneğini başlatır **Module::MethodReleaseNotifier** sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
MethodReleaseNotifier(  
   _In_ T* object,   
   _In_ void (T::* method)(),   
   bool release) throw() :  
            ReleaseNotifier(release), object_(object),   
            method_(method);  
```  
  
### <a name="parameters"></a>Parametreler  
 *object*  
 Bir olay işleyicisi üye işlevi olan nesne.  
  
 *Yöntemi*  
 Üye işlevi parametresinin *nesne* yani olay işleyicisi.  
  
 *Yayın*  
 Belirtin **true** temel çağırma etkinleştirmek için [Modülü:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) yöntemi; Aksi takdirde belirtin **false**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Module::MethodReleaseNotifier Sınıfı](../windows/module-methodreleasenotifier-class.md)