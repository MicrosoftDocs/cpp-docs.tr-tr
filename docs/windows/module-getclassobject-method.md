---
title: Module::GetClassObject metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetClassObject
dev_langs:
- C++
helpviewer_keywords:
- GetClassObject method
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e0c8996823de35bbfd85d595556db933f34238a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599228"
---
# <a name="modulegetclassobject-method"></a>Module::GetClassObject Metodu

Sınıf üreteçlerini önbelleğini Retreives.

## <a name="syntax"></a>Sözdizimi

```cpp
 HRESULT GetClassObject(
   REFCLSID clsid,
   REFIID riid,
   _Deref_out_ void **ppv,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Parametreler

*CLSID*  
Sınıf kimliği

*riid*  
İstek, arabirim kimliği.

*ppv*  
Döndürülen nesne işaretçisi.

*SunucuAdı*  
Ya da belirtilen sunucu adı `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx`, veya `ActivatableClass` makrosu; veya **nullptr** varsayılan sunucu adı alınamıyor.

## <a name="return-value"></a>Dönüş Değeri

## <a name="remarks"></a>Açıklamalar

Yalnızca COM için değil Windows çalışma zamanı bu yöntemi kullanın. Bu yöntem yalnızca sunan `IClassFactory` yöntemleri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.
[Modül Sınıfı](../windows/module-class.md)