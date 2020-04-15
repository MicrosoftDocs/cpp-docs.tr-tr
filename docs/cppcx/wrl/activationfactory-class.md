---
title: ActivationFactory Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::AddRef
- module/Microsoft::WRL::ActivationFactory::GetIids
- module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
- module/Microsoft::WRL::ActivationFactory::QueryInterface
- module/Microsoft::WRL::ActivationFactory::Release
helpviewer_keywords:
- Microsoft::WRL::ActivationFactory class
- Microsoft::WRL::ActivationFactory::ActivationFactory, constructor
- Microsoft::WRL::ActivationFactory::AddRef method
- Microsoft::WRL::ActivationFactory::GetIids method
- Microsoft::WRL::ActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::ActivationFactory::GetTrustLevel method
- Microsoft::WRL::ActivationFactory::QueryInterface method
- Microsoft::WRL::ActivationFactory::Release method
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
ms.openlocfilehash: 0655caeb3f49a18e9c57c78f0008901aaaedda4a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368701"
---
# <a name="activationfactory-class"></a>ActivationFactory Sınıfı

Bir veya daha fazla sınıfın Windows Runtime tarafından etkinleştirilmesini sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ActivationFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IActivationFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<WinRt | InhibitWeakReference>,
        false
    >;
```

### <a name="parameters"></a>Parametreler

*I0*<br/>
Sıfırın arabirimi.

*I1*<br/>
İlk arayüz.

*I2*<br/>
İkinci arayüz.

## <a name="remarks"></a>Açıklamalar

`ActivationFactory``IActivationFactory` arayüz için kayıt yöntemleri ve temel işlevsellik sağlar. `ActivationFactory`ayrıca özel bir fabrika uygulaması sağlamanızı sağlar.

Aşağıdaki kod parçası sembolik olarak Etkinleştirme Fabrikası'nın nasıl kullanılacağını göstermektedir.

[!code-cpp[wrl-microsoft__wrl__activationfactory#1](../codesnippet/CPP/activationfactory-class_1.cpp)]

Aşağıdaki kod parçası, üçten fazla arabirim dis'i belirtmek için [Uygulamalar](implements-structure.md) yapısının nasıl kullanılacağını gösterir.

`struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                                       | Açıklama
---------------------------------------------------------- | ------------------------------------------
[AktivasyonFabrika::AktivasyonFabrikası](#activationfactory) | Sınıfı başharfe iter. `ActivationFactory`

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                                           | Açıklama
-------------------------------------------------------------- | --------------------------------------------------------------------------------------------
[AktivasyonFabrika::AddRef](#addref)                           | Geçerli nesnenin başvuru sayısını artırımına eder. `ActivationFactory`
[ActivationFactory::GetIids](#getiids)                         | Uygulanan arabirim işlemi dizilimial eder.
[ActivationFactory::GetRuntimeClassName](#getruntimeclassname) | Geçerli `ActivationFactory` anlık olarak anlaştığı nesnenin çalışma zamanı sınıf adını alır.
[AktivasyonFabrika::GetTrustLevel](#gettrustlevel)             | Geçerli `ActivationFactory` anlık nesnenin güven düzeyini alır.
[ActivationFactory::QueryInterface](#queryinterface)           | Belirtilen arabirime bir işaretçi alır.
[ActivationFactory::Yayın](#release)                         | Geçerli `ActivationFactory` nesnenin başvuru sayısını eriter.

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

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** module.h

**Ad alanı:** Microsoft::WRL

## <a name="activationfactoryactivationfactory"></a><a name="activationfactory"></a>AktivasyonFabrika::AktivasyonFabrikası

Sınıfı başharfe iter. `ActivationFactory`

```cpp
ActivationFactory();
```

## <a name="activationfactoryaddref"></a><a name="addref"></a>AktivasyonFabrika::AddRef

Geçerli nesnenin başvuru sayısını artırımına eder. `ActivationFactory`

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, başarısızlığı açıklayan bir HRESULT.

## <a name="activationfactorygetiids"></a><a name="getiids"></a>ActivationFactory::GetIids

Uygulanan arabirim işlemi dizilimial eder.

```cpp
STDMETHOD(
   GetIids
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Parametreler

*iidSay*<br/>
Bu işlem tamamlandığında, *iids* dizisinde interace kimlikleri sayısı.

*iids*<br/>
Bu işlem tamamlandığında, uygulanan arabirim işl

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, başarısızlığı açıklayan bir HRESULT. E_OUTOFMEMORY olası bir başarısızlık HRESULT olduğunu.

## <a name="activationfactorygetruntimeclassname"></a><a name="getruntimeclassname"></a>ActivationFactory::GetRuntimeClassName

Geçerli `ActivationFactory` anlık olarak anlaştığı nesnenin çalışma zamanı sınıf adını alır.

```cpp
STDMETHOD(
   GetRuntimeClassName
)(_Out_ HSTRING* runtimeName);
```

### <a name="parameters"></a>Parametreler

*runtimeName*<br/>
Bu işlem tamamlandığında, geçerli `ActivationFactory` anlık nesnenin çalışma zamanı sınıf adını içeren bir dize bir tutamaç.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, başarısızlığı açıklayan bir HRESULT.

## <a name="activationfactorygettrustlevel"></a><a name="gettrustlevel"></a>AktivasyonFabrika::GetTrustLevel

Geçerli `ActivationFactory` anlık nesnenin güven düzeyini alır.

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>Parametreler

*güvenLvl*<br/>
Bu işlem tamamlandığında, çalışma zamanı sınıfının güven `ActivationFactory` düzeyi anında gerçekleşir.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, bir iddia hatası yayılır ve *trustLvl* `FullTrust`ayarlanır.

## <a name="activationfactoryqueryinterface"></a><a name="queryinterface"></a>ActivationFactory::QueryInterface

Belirtilen arabirime bir işaretçi alır.

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Parametreler

*Riid*<br/>
Arayüz kimliği.

*ppvNesne*<br/>
Bu işlem tamamlandığında, parametre *riid*tarafından belirtilen arabirimin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, başarısızlığı açıklayan bir HRESULT.

## <a name="activationfactoryrelease"></a><a name="release"></a>ActivationFactory::Yayın

Geçerli `ActivationFactory` nesnenin başvuru sayısını eriter.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, başarısızlığı açıklayan bir HRESULT.
