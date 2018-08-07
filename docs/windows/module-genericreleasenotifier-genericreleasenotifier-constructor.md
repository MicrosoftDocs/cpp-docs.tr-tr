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
ms.openlocfilehash: b0683220710a62c8583fa95fbfe3221ae93307eb
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603944"
---
# <a name="modulegenericreleasenotifiergenericreleasenotifier-constructor"></a>Module::GenericReleaseNotifier::GenericReleaseNotifier Oluşturucusu
Yeni bir örneğini başlatır **Module::GenericReleaseNotifier** sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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