---
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
ms.openlocfilehash: 39e539c63e91b508f51656114ee8fbd68150991f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370946"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory Sınıfı

Windows Runtime veya klasik COM taban sınıfı oluşturmak için temel bir mekanizma sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Base>
class SimpleActivationFactory : public ActivationFactory<>;
```

### <a name="parameters"></a>Parametreler

*Temel*<br/>
Taban sınıf.

## <a name="remarks"></a>Açıklamalar

Taban sınıf varsayılan bir oluşturucu sağlaması gerekir.

Aşağıdaki kod [örneği, ActivatableClassWithFactoryEx](activatableclass-macros.md) makrosuyla SimpleActivationFactory'nin nasıl kullanılacağını göstermektedir.

`ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[SimpleActivationFactory::ActivateInstance Metodu](#activateinstance)|Belirtilen arabirimin bir örneğini oluşturur.|
|[SimpleActivationFactory::GetRuntimeClassName Metodu](#getruntimeclassname)|*Taban* sınıf şablonu parametresi tarafından belirtilen sınıfın bir örneğinin çalışma zamanı sınıf adını alır.|
|[SimpleActivationFactory::GetTrustLevel Metodu](#gettrustlevel)|*Base* sınıfı şablon parametresi tarafından belirtilen sınıfın bir örneğinin güven düzeyini alır.|

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

**Üstbilgi:** module.h

**Ad alanı:** Microsoft::WRL

## <a name="simpleactivationfactoryactivateinstance-method"></a><a name="activateinstance"></a>SimpleActivationFactory::ActivateInstance Yöntemi

Belirtilen arabirimin bir örneğini oluşturur.

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

#### <a name="parameters"></a>Parametreler

*ppvNesne*<br/>
Bu işlem tamamlandığında, sınıf şablonu parametresi `Base` tarafından belirtilen nesnenin bir örneğini işaretleyin.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

`__WRL_STRICT__` Tanımlanırsa, sınıf şablonu parametresinde belirtilen taban sınıf [RuntimeClass'tan](runtimeclass-class.md)türetilmemişse veya WinRtRt veya WinRtClassicComMix [RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırma değeriyle yapılandırılmamışsa bir ileri savunma hatası yayımlanır.

## <a name="simpleactivationfactorygetruntimeclassname-method"></a><a name="getruntimeclassname"></a>SimpleActivationFactory::GetRuntimeClassName Yöntemi

`Base` Sınıf şablonu parametresi tarafından belirtilen sınıfın bir örneğinin çalışma zamanı sınıf adını alır.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

#### <a name="parameters"></a>Parametreler

*runtimeName*<br/>
Bu işlem tamamlandığında, çalışma zamanı sınıf adı.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

`__WRL_STRICT__` `Base` Tanımlanırsa, sınıf şablonu parametresi tarafından belirtilen sınıf [RuntimeClass'tan](runtimeclass-class.md)türetilmemişse veya WinRtRt veya WinRtClassicComMix [RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırma değeriyle yapılandırılmamışsa, bir ileri assert hatası yayımlanır.

## <a name="simpleactivationfactorygettrustlevel-method"></a><a name="gettrustlevel"></a>SimpleActivationFactory::GetTrustLevel Yöntemi

`Base` Sınıf şablonu parametresi tarafından belirtilen sınıfın bir örneğinin güven düzeyini alır.

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

#### <a name="parameters"></a>Parametreler

*güvenLvl*<br/>
Bu işlem tamamlandığında, geçerli sınıf nesnesinin güven düzeyi.

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK.
