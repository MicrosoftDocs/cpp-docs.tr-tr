---
description: 'Daha fazla bilgi edinin: SimpleActivationFactory sınıfı'
title: SimpleActivationFactory Sınıfı
ms.date: 09/07/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
helpviewer_keywords:
- Microsoft::WRL::SimpleActivationFactory class
- Microsoft::WRL::SimpleActivationFactory::ActivateInstance method
- Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::SimpleActivationFactory::GetTrustLevel method
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
ms.openlocfilehash: 83643c69977b887e58e430bbd500fcf7c2e81ca6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135219"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory Sınıfı

Windows Çalışma Zamanı veya klasik COM temel sınıfı oluşturmak için temel bir mekanizma sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Base>
class SimpleActivationFactory : public ActivationFactory<>;
```

### <a name="parameters"></a>Parametreler

*Temel*<br/>
Temel sınıf.

## <a name="remarks"></a>Açıklamalar

Temel sınıf varsayılan bir Oluşturucu sağlamalıdır.

Aşağıdaki kod örneğinde, [ActivatableClassWithFactoryEx](activatableclass-macros.md) makrosu Ile SimpleActivationFactory 'nin nasıl kullanılacağı gösterilmektedir.

`ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[SimpleActivationFactory::ActivateInstance Metodu](#activateinstance)|Belirtilen arabirimin bir örneğini oluşturur.|
|[SimpleActivationFactory::GetRuntimeClassName Metodu](#getruntimeclassname)|*Temel* sınıf şablonu parametresi tarafından belirtilen sınıf örneğinin çalışma zamanı sınıf adını alır.|
|[SimpleActivationFactory::GetTrustLevel Metodu](#gettrustlevel)|*Temel* sınıf şablonu parametresi tarafından belirtilen sınıfın bir örneğinin güven düzeyini alır.|

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

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL

## <a name="simpleactivationfactoryactivateinstance-method"></a><a name="activateinstance"></a> SimpleActivationFactory:: ActivateInstance yöntemi

Belirtilen arabirimin bir örneğini oluşturur.

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

#### <a name="parameters"></a>Parametreler

*ppvObject*<br/>
Bu işlem tamamlandığında, sınıf şablonu parametresi tarafından belirtilen nesnenin örneğine yönelik işaretçi `Base` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

`__WRL_STRICT__`Tanımlanmışsa, sınıf şablonu parametresinde belirtilen temel sınıf [RuntimeClass](runtimeclass-class.md)'dan türetilmemişse veya WinRT ya da WinRtClassicComMix [RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırma değeriyle yapılandırılmamışsa bir onaylama hatası yayınlanır.

## <a name="simpleactivationfactorygetruntimeclassname-method"></a><a name="getruntimeclassname"></a> SimpleActivationFactory:: GetRuntimeClassName yöntemi

Sınıf şablonu parametresi tarafından belirtilen sınıf örneğinin çalışma zamanı sınıf adını alır `Base` .

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

#### <a name="parameters"></a>Parametreler

*runtimeName*<br/>
Bu işlem tamamlandığında, çalışma zamanı sınıf adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

`__WRL_STRICT__`Tanımlanmışsa, `Base` sınıf şablonu parametresi tarafından belirtilen sınıf [RuntimeClass](runtimeclass-class.md)'Dan türetilmemişse veya WinRT ya da WinRtClassicComMix [RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırma değeriyle yapılandırılmamışsa bir onaylama hatası yayınlanır.

## <a name="simpleactivationfactorygettrustlevel-method"></a><a name="gettrustlevel"></a> SimpleActivationFactory:: GetTrustLevel Yöntemi

Sınıf şablonu parametresi tarafından belirtilen sınıfın bir örneğinin güven düzeyini alır `Base` .

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

#### <a name="parameters"></a>Parametreler

*trustLvl*<br/>
Bu işlem tamamlandığında, geçerli sınıf nesnesinin güven düzeyi.

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK.
