---
title: "Module::genericreleasenotifier:: genericreleasenotifier Oluşturucusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
dev_langs: C++
helpviewer_keywords: GenericReleaseNotifier, constructor
ms.assetid: feb5b687-a4b0-4809-9022-8f292181b7a1
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f0309040b64614280d2314daa83c5919514b3fb6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Module::GenericReleaseNotifier sınıfı](../windows/module-genericreleasenotifier-class.md)