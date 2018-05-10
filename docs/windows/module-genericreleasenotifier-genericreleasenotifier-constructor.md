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
ms.openlocfilehash: bb07c7f53e27e380ba5775369611299cad0f60d4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="modulegenericreleasenotifiergenericreleasenotifier-constructor"></a>Module::GenericReleaseNotifier::GenericReleaseNotifier Oluşturucusu
Module::GenericReleaseNotifier sınıfının yeni bir örneğini başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      GenericReleaseNotifier(  
   T callback,   
   bool release  
) throw() : ReleaseNotifier(release), callback_(callback);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `callback`  
 Lambda, functor veya parantez işlevi operatörüyle çağrılabilir işaretçi işlevi olay işleyicisi (`()`).  
  
 `release`  
 Belirtin `true` arka plandaki çağırma etkinleştirmek için [Modülü:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) yöntemi; Aksi takdirde belirtin `false`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Module::GenericReleaseNotifier Sınıfı](../windows/module-genericreleasenotifier-class.md)