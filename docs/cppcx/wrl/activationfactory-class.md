---
description: 'Daha fazla bilgi edinin: ActivationFactory sınıfı'
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
ms.openlocfilehash: 7204a3c2f981947a03efba648dd91b69d582fee1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287846"
---
# <a name="activationfactory-class"></a>ActivationFactory Sınıfı

Windows Çalışma Zamanı tarafından bir veya daha fazla sınıfın etkinleştirilmesini sağlar.

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
Diğer arabirim.

*I1*<br/>
İlk arabirim.

*I2*<br/>
İkinci arabirim.

## <a name="remarks"></a>Açıklamalar

`ActivationFactory` arabirim için kayıt yöntemleri ve temel işlevleri sağlar `IActivationFactory` . `ActivationFactory` Ayrıca özel bir fabrika uygulamasını sağlamanıza olanak sağlar.

Aşağıdaki kod parçası,, ActivationFactory 'yi nasıl kullanacağınızı gösterir.

[!code-cpp[wrl-microsoft__wrl__activationfactory#1](../codesnippet/CPP/activationfactory-class_1.cpp)]

Aşağıdaki kod parçası, en fazla üç arabirim kimliği belirtmek için [Implements](implements-structure.md) yapısının nasıl kullanılacağını gösterir.

`struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                       | Açıklama
---------------------------------------------------------- | ------------------------------------------
[ActivationFactory:: ActivationFactory](#activationfactory) | Sınıfını başlatır `ActivationFactory` .

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                           | Açıklama
-------------------------------------------------------------- | --------------------------------------------------------------------------------------------
[ActivationFactory:: AddRef](#addref)                           | Geçerli nesnenin başvuru sayısını artırır `ActivationFactory` .
[ActivationFactory:: Getııds](#getiids)                         | Uygulanan bir arabirim kimlikleri dizisini alır.
[ActivationFactory:: GetRuntimeClassName](#getruntimeclassname) | Geçerli örnekleyen nesnenin çalışma zamanı sınıf adını alır `ActivationFactory` .
[ActivationFactory:: GetTrustLevel](#gettrustlevel)             | Geçerli örnekleyen nesnenin güven düzeyini alır `ActivationFactory` .
[ActivationFactory:: QueryInterface](#queryinterface)           | Belirtilen arabirime bir işaretçi alır.
[ActivationFactory:: Release](#release)                         | Geçerli nesnenin başvuru sayısını azaltır `ActivationFactory` .

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

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL

## <a name="activationfactoryactivationfactory"></a><a name="activationfactory"></a> ActivationFactory:: ActivationFactory

Sınıfını başlatır `ActivationFactory` .

```cpp
ActivationFactory();
```

## <a name="activationfactoryaddref"></a><a name="addref"></a> ActivationFactory:: AddRef

Geçerli nesnenin başvuru sayısını artırır `ActivationFactory` .

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

## <a name="activationfactorygetiids"></a><a name="getiids"></a> ActivationFactory:: Getııds

Uygulanan bir arabirim kimlikleri dizisini alır.

```cpp
STDMETHOD(
   GetIids
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Parametreler

*IidCount*<br/>
Bu işlem tamamlandığında, *IIDS* dizisindeki ınterace kimliklerinin sayısı.

*IID*<br/>
Bu işlem tamamlandığında, uygulanan bir arabirim kimlikleri dizisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT. E_OUTOFMEMORY, HRESULT bir hata olabilir.

## <a name="activationfactorygetruntimeclassname"></a><a name="getruntimeclassname"></a> ActivationFactory:: GetRuntimeClassName

Geçerli örnekleyen nesnenin çalışma zamanı sınıf adını alır `ActivationFactory` .

```cpp
STDMETHOD(
   GetRuntimeClassName
)(_Out_ HSTRING* runtimeName);
```

### <a name="parameters"></a>Parametreler

*runtimeName*<br/>
Bu işlem tamamlandığında, geçerli örnekleyen nesnenin çalışma zamanı sınıf adını içeren bir dizeye yönelik bir tanıtıcı `ActivationFactory` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

## <a name="activationfactorygettrustlevel"></a><a name="gettrustlevel"></a> ActivationFactory:: GetTrustLevel

Geçerli örnekleyen nesnenin güven düzeyini alır `ActivationFactory` .

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>Parametreler

*trustLvl*<br/>
Bu işlem tamamlandığında, tarafından örnekleyen çalışma zamanı sınıfının güven düzeyi `ActivationFactory` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, bir onaylama hatası yayınlanır ve *trustLvl* olarak ayarlanır `FullTrust` .

## <a name="activationfactoryqueryinterface"></a><a name="queryinterface"></a> ActivationFactory:: QueryInterface

Belirtilen arabirime bir işaretçi alır.

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Parametreler

*riıd*<br/>
Arabirim KIMLIĞI.

*ppvObject*<br/>
Bu işlem tamamlandığında, parametre *riıd* tarafından belirtilen arabirime yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

## <a name="activationfactoryrelease"></a><a name="release"></a> ActivationFactory:: Release

Geçerli nesnenin başvuru sayısını azaltır `ActivationFactory` .

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.
