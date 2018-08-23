---
title: Module::GetActivationFactory metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory method
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0e87ea3b0e44732d4271385073c48fd92e1aa114
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42608933"
---
# <a name="modulegetactivationfactory-method"></a>Module::GetActivationFactory Metodu

Etkinleştirme fabrikası için modülü alır.

## <a name="syntax"></a>Sözdizimi

```cpp
WRL_NOTHROW HRESULT GetActivationFactory(
   _In_ HSTRING pActivatibleClassId,
   _Deref_out_ IActivationFactory **ppIFactory,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Parametreler

*pActivatibleClassId*  
Laboratuvardaki bir çalışma zamanı sınıf.

*ppIFactory*  
Belirtilen çalışma zamanı sınıfının IActivationFactory.

*SunucuAdı*  
Sınıf üreteçlerini geçerli modüldeki bir alt kümesi adı. Kullanılan sunucu adını belirtmek [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) makro veya belirtin **nullptr** varsayılan sunucu adı alınamıyor.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde GetActivationFactory tarafından döndürülen HRESULT.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Modül Sınıfı](../windows/module-class.md)  
[ActivatableClass Makroları](../windows/activatableclass-macros.md)