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
ms.openlocfilehash: 995594ee48e6ca408e88d9ab14968d88b536d309
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403522"
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

*pActivatibleClassId*<br/>
Laboratuvardaki bir çalışma zamanı sınıf.

*ppIFactory*<br/>
Belirtilen çalışma zamanı sınıfının IActivationFactory.

*SunucuAdı*<br/>
Sınıf üreteçlerini geçerli modüldeki bir alt kümesi adı. Kullanılan sunucu adını belirtmek [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) makro veya belirtin **nullptr** varsayılan sunucu adı alınamıyor.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde GetActivationFactory tarafından döndürülen HRESULT.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Modül Sınıfı](../windows/module-class.md)<br/>
[ActivatableClass Makroları](../windows/activatableclass-macros.md)