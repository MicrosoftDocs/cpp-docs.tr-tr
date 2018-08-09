---
title: Module::UnregisterWinRTObject yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterWinRTObject
dev_langs:
- C++
helpviewer_keywords:
- UnregisterWinRTObject method
ms.assetid: 32334aa7-2293-40d2-9a89-4b02e2e31f3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 93c804f9e7701ab3bf021902b62ae3f1b414d61c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019085"
---
# <a name="moduleunregisterwinrtobject-method"></a>Module::UnregisterWinRTObject Yöntemi
Böylece diğer uygulamalar için bağlanılamıyor veya daha fazla Windows çalışma zamanı nesne kaydını siler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
virtual HRESULT UnregisterWinRTObject(  
   unsigned int,  
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *Tanımlama bilgisi*  
 Kaydını iptal edilmesine izin sınıfı nesne tanımlayan bir değer için bir işaretçi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül Sınıfı](../windows/module-class.md)