---
title: SimpleActivationFactory sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/07/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::SimpleActivationFactory class
- Microsoft::WRL::SimpleActivationFactory::ActivateInstance method
- Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::SimpleActivationFactory::GetTrustLevel method
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 111015fdd8887ae779aeb8fecc8274cfcf7c6c68
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441284"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory Sınıfı

Bir Windows çalışma zamanı veya klasik COM temel sınıfı oluşturmak için temel bir mekanizma sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Base>
class SimpleActivationFactory : public ActivationFactory<>;
```

### <a name="parameters"></a>Parametreler

*temel*<br/>
Temel sınıf.

## <a name="remarks"></a>Açıklamalar

Temel sınıfın varsayılan bir oluşturucu sağlamanız gerekir.

Aşağıdaki kod örneği ile SimpleActivationFactory kullanımı gösterilmiştir [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) makrosu.

`ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[SimpleActivationFactory::ActivateInstance Metodu](#activateinstance)|Belirtilen arabirim bir örneğini oluşturur.|
|[SimpleActivationFactory::GetRuntimeClassName Metodu](#getruntimeclassname)|Çalışma zamanı sınıf adı tarafından belirtilen sınıfın örneğini alır *temel* sınıfı şablon parametresi.|
|[SimpleActivationFactory::GetTrustLevel Metodu](#gettrustlevel)|Tarafından belirtilen sınıfın bir örneği güven düzeyini alır *temel* sınıfı şablon parametresi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ActivationFactory`

`SimpleActivationFactory`

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="activateinstance"></a>Simpleactivationfactory::activateınstance yöntemi

Belirtilen arabirim bir örneğini oluşturur.

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

#### <a name="parameters"></a>Parametreler

*ppvObject*<br/>
Bu işlem tamamlandığında, işaretçi tarafından belirtilen nesnede örneğine `Base` sınıfı şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Varsa `__WRL_STRICT__` olan tanımlanan, türetilen sınıf şablonu parametresinde belirtilen temel sınıf değil, bir onay hata yayıldığını [RuntimeClass](../windows/runtimeclass-class.md), ya da WinRt veya WinRtClassicComMix ile yapılandırılmamış [ RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırma değeri.

## <a name="getruntimeclassname"></a>SimpleActivationFactory::GetRuntimeClassName metodu

Çalışma zamanı sınıf adı tarafından belirtilen sınıfın örneğini alır `Base` sınıfı şablon parametresi.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

#### <a name="parameters"></a>Parametreler

*runtimeName*<br/>
Bu işlem tamamlandığında, çalışma zamanı sınıf adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Varsa `__WRL_STRICT__` olan sınıfın belirtilen tanımlanan, bir onay hatası yayılır `Base` olmayan şablon parametresi sınıf türetilmiş [RuntimeClass](../windows/runtimeclass-class.md), ya da WinRt veya WinRtClassicComMix ileyapılandırılmamış[RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırma değeri.

## <a name="gettrustlevel"></a>SimpleActivationFactory::GetTrustLevel metodu

Tarafından belirtilen sınıfın bir örneği güven düzeyini alır `Base` sınıfı şablon parametresi.

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

#### <a name="parameters"></a>Parametreler

*trustLvl*<br/>
Bu işlem tamamlandığında geçerli sınıf nesnesi güven düzeyi.

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK.
