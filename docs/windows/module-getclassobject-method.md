---
title: "Module::GetClassObject yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::GetClassObject
dev_langs: C++
helpviewer_keywords: GetClassObject method
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1ad48700b1a7d2a4ca516e5df98a6ac2e0dd0b78
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="modulegetclassobject-method"></a>Module::GetClassObject Metodu
Sınıf oluşturucuları önbelleği Retreives.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
 HRESULT GetClassObject(  
   REFCLSID clsid,  
   REFIID riid,  
   _Deref_out_ void **ppv,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `clsid`  
 Sınıf kimliği  
  
 `riid`  
 Arabirim, isteği kimliği.  
  
 `ppv`  
 İşaretçi Nesne döndürdü.  
  
 `serverName`  
 Ya da belirtilen sunucu adı `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx`, veya `ActivatableClass` makrosu; veya `nullptr` varsayılan sunucu adı alınamıyor.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca COM, değil Windows çalışma zamanı kullanın. Bu yöntem yalnızca IClassFactory yöntemlerini gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül sınıfı](../windows/module-class.md)