---
title: "Module::methodreleasenotifier:: methodreleasenotifier Oluşturucusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
dev_langs: C++
helpviewer_keywords: MethodReleaseNotifier, constructor
ms.assetid: 762e2ca4-0a92-49de-9ff5-d3efa0f067c0
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d40c05faa3ecc551904d2f267078ba342ea42b46
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="modulemethodreleasenotifiermethodreleasenotifier-constructor"></a>Module::MethodReleaseNotifier::MethodReleaseNotifier Oluşturucusu
Module::MethodReleaseNotifier sınıfının yeni bir örneğini başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
MethodReleaseNotifier(  
   _In_ T* object,   
   _In_ void (T::* method)(),   
   bool release) throw() :  
            ReleaseNotifier(release), object_(object),   
            method_(method);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `object`  
 Olay işleyici, üye işlevi olan bir nesne.  
  
 `method`  
 Üye işlevini parametresinin `object` diğer bir deyişle olay işleyicisi.  
  
 `release`  
 Belirtin `true` arka plandaki çağırma etkinleştirmek için [Modülü:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) yöntemi; Aksi takdirde belirtin `false`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Module::MethodReleaseNotifier sınıfı](../windows/module-methodreleasenotifier-class.md)