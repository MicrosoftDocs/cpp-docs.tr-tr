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
ms.openlocfilehash: 8e5132f4a8711f6420cd9b52751550a96d10d8fc
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787846"
---
# <a name="activationfactory-class"></a>ActivationFactory Sınıfı

Windows çalışma zamanı tarafından etkinleştirilmesi bir veya daha fazla sınıflar sağlar.

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
Sıfırıncı arabirim.

*I1*<br/>
İlk arabirim.

*I2*<br/>
İkinci arabirim.

## <a name="remarks"></a>Açıklamalar

`ActivationFactory` Kayıt yöntemleri ve için temel işlevleri sağlayan `IActivationFactory` arabirimi. `ActivationFactory` Ayrıca özel Üreteç uygulaması girmenize olanak tanır.

Aşağıdaki kod parçası bildirmelerine ActivationFactory kullanılması gösterilmektedir.

[!code-cpp[wrl-microsoft__wrl__activationfactory#1](../codesnippet/CPP/activationfactory-class_1.cpp)]

Aşağıdaki kod parçası nasıl kullanılacağını gösterir [uygular](implements-structure.md) yapısı üçten fazla arabirim kimliklerini belirtin.

`struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                       | Açıklama
---------------------------------------------------------- | ------------------------------------------
[ActivationFactory::ActivationFactory](#activationfactory) | Başlatır `ActivationFactory` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                           | Açıklama
-------------------------------------------------------------- | --------------------------------------------------------------------------------------------
[ActivationFactory::AddRef](#addref)                           | Geçerli başvuru sayısını artırır `ActivationFactory` nesne.
[Activationfactory::getıids](#getiids)                         | Uygulanan arabirimi kimlikleri dizisini alır.
[ActivationFactory::GetRuntimeClassName](#getruntimeclassname) | Nesnenin çalışma zamanı sınıf adını alır Geçerli `ActivationFactory` başlatır.
[ActivationFactory::GetTrustLevel](#gettrustlevel)             | Nesne güven düzeyini alır Geçerli `ActivationFactory` başlatır.
[Activationfactory::QueryInterface](#queryinterface)           | Belirtilen arabirim işaretçisi alır.
[ActivationFactory::Release](#release)                         | Başvuru sayma geçerli azaltır `ActivationFactory` nesne.

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

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="activationfactory"></a>ActivationFactory::ActivationFactory

Başlatır `ActivationFactory` sınıfı.

```cpp
ActivationFactory();
```

## <a name="addref"></a>ActivationFactory::AddRef

Geçerli başvuru sayısını artırır `ActivationFactory` nesne.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

## <a name="getiids"></a>Activationfactory::getıids

Uygulanan arabirimi kimlikleri dizisini alır.

```cpp
STDMETHOD(
   GetIids
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Parametreler

*Iidcount*<br/>
Bu işlem tamamlandığında, nesneniz kimlikleri sayısı *IID'leri* dizisi.

*IID'leri*<br/>
Bu işlem tamamlandığında, bir dizi arabirim kimlikleri uygulanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT. E_OUTOFMEMORY olası bir hata HRESULT ' dir.

## <a name="getruntimeclassname"></a>ActivationFactory::GetRuntimeClassName

Nesnenin çalışma zamanı sınıf adını alır Geçerli `ActivationFactory` başlatır.

```cpp
STDMETHOD(
   GetRuntimeClassName
)(_Out_ HSTRING* runtimeName);
```

### <a name="parameters"></a>Parametreler

*runtimeName*<br/>
Bu işlem tamamlandığında, nesnenin çalışma zamanı sınıfının adını içeren bir dize için bir tanıtıcı, geçerli `ActivationFactory` başlatır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

## <a name="gettrustlevel"></a>ActivationFactory::GetTrustLevel

Nesne güven düzeyini alır Geçerli `ActivationFactory` başlatır.

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>Parametreler

*trustLvl*<br/>
Bu işlem tamamlandığında, çalışma zamanı güven düzeyini sınıfı, `ActivationFactory` başlatır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, bir onaylama işlemi hatası yayılır ve *trustLvl* ayarlanır `FullTrust`.

## <a name="queryinterface"></a>Activationfactory::QueryInterface

Belirtilen arabirim işaretçisi alır.

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Parametreler

*riid*<br/>
Bir arabirim kimliği.

*ppvObject*<br/>
Bu işlem tamamlandığında, parametre tarafından belirtilen arabirim işaretçisi *riid*.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

## <a name="release"></a>ActivationFactory::Release

Başvuru sayma geçerli azaltır `ActivationFactory` nesne.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.
