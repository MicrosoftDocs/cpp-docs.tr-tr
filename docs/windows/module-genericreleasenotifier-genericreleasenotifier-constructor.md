---
title: 'Module::genericreleasenotifier:: genericreleasenotifier Oluşturucusu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- GenericReleaseNotifier, constructor
ms.assetid: feb5b687-a4b0-4809-9022-8f292181b7a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5aa78562c934c41b2ff2ab7b381f6b2612426651
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014594"
---
# <a name="modulegenericreleasenotifiergenericreleasenotifier-constructor"></a>Module::GenericReleaseNotifier::GenericReleaseNotifier Oluşturucusu
Yeni bir örneğini başlatır **Module::GenericReleaseNotifier** sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
GenericReleaseNotifier(  
   T callback,   
   bool release  
) throw() : ReleaseNotifier(release), callback_(callback);  
```  
  
### <a name="parameters"></a>Parametreler  
 *geri çağırma*  
 Bir lambda, functor veya parantez işlevi işleci ile çağrılabilir işaretçi işlevi olay işleyicisi (`()`).  
  
 *Yayın*  
 Belirtin **true** temel çağırma etkinleştirmek için [Modülü:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) yöntemi; Aksi takdirde belirtin **false**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Module::GenericReleaseNotifier Sınıfı](../windows/module-genericreleasenotifier-class.md)