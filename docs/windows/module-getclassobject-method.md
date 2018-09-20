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
ms.openlocfilehash: 90a1b527d12e581c42fc9519e56d453f845e0b63
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419730"
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

*CLSID*<br/>
Sınıf kimliği

*riid*<br/>
İstek, arabirim kimliği.

*ppv*<br/>
Döndürülen nesne işaretçisi.

*SunucuAdı*<br/>
Ya da belirtilen sunucu adı `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx`, veya `ActivatableClass` makrosu; veya **nullptr** varsayılan sunucu adı alınamıyor.

## <a name="return-value"></a>Dönüş Değeri

## <a name="remarks"></a>Açıklamalar

Yalnızca COM için değil Windows çalışma zamanı bu yöntemi kullanın. Bu yöntem yalnızca sunan `IClassFactory` yöntemleri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Modül Sınıfı](../windows/module-class.md)