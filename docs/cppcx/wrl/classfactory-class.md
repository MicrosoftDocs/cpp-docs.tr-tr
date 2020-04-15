---
title: ClassFactory Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory
- module/Microsoft::WRL::ClassFactory::AddRef
- module/Microsoft::WRL::ClassFactory::ClassFactory
- module/Microsoft::WRL::ClassFactory::LockServer
- module/Microsoft::WRL::ClassFactory::QueryInterface
- module/Microsoft::WRL::ClassFactory::Release
helpviewer_keywords:
- Microsoft::WRL::ClassFactory class
- Microsoft::WRL::ClassFactory::AddRef method
- Microsoft::WRL::ClassFactory::ClassFactory, constructor
- Microsoft::WRL::ClassFactory::LockServer method
- Microsoft::WRL::ClassFactory::QueryInterface method
- Microsoft::WRL::ClassFactory::Release method
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
ms.openlocfilehash: 3b738cc8f439e6653162ab99b0a26e87aa8fee36
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372673"
---
# <a name="classfactory-class"></a>ClassFactory Sınıfı

`IClassFactory` Arabirimin temel işlevselliğini uygular.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ClassFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IClassFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<ClassicCom | InhibitWeakReference>,
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

Kullanıcı `ClassFactory` tanımlı bir fabrika uygulaması sağlamak için yararlanın.

Aşağıdaki programlama deseni, bir sınıf fabrikasında üçten fazla arabirim belirtmek için [Uygulamalar](implements-structure.md) yapısının nasıl kullanılacağını gösterir.

`struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                        | Açıklama
------------------------------------------- | -----------
[ClassFactory::ClassFactory](#classfactory) |

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                            | Açıklama
----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------
[ClassFactory::Addref](#addref)                 | Geçerli `ClassFactory` nesne için başvuru sayısını artırımı.
[ClassFactory::LockServer](#lockserver)         | Geçerli `ClassFactory` nesne tarafından izlenen temel nesnelerin sayısını artışlar veya bunlar ayarı.
[ClassFactory::QueryInterface](#queryinterface) | Parametre ile belirtilen arabirime bir işaretçi alır.
[ClassFactory::Sürüm](#release)               | Geçerli `ClassFactory` nesne için başvuru sayısını eriter.

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

`ClassFactory`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** module.h

**Ad alanı:** Microsoft::WRL

## <a name="classfactoryaddref"></a><a name="addref"></a>ClassFactory::Addref

Geçerli `ClassFactory` nesne için başvuru sayısını artırımı.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, başarısızlığı açıklayan bir HRESULT.

## <a name="classfactoryclassfactory"></a><a name="classfactory"></a>ClassFactory::ClassFactory

```cpp
WRL_NOTHROW ClassFactory();
```

## <a name="classfactorylockserver"></a><a name="lockserver"></a>ClassFactory::LockServer

Geçerli `ClassFactory` nesne tarafından izlenen temel nesnelerin sayısını artışlar veya bunlar ayarı.

```cpp
STDMETHOD(
   LockServer
)(BOOL fLock);
```

### <a name="parameters"></a>Parametreler

*Sürü*<br/>
**true** izlenen nesnelerin sayısını n için doğru. izlenen nesnelerin sayısını vermek için **yanlış.**

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, E_FAIL.

### <a name="remarks"></a>Açıklamalar

`ClassFactory`[Modül](module-class.md) sınıfının altında yatan bir örnekteki nesneleri izler.

## <a name="classfactoryqueryinterface"></a><a name="queryinterface"></a>ClassFactory::QueryInterface

Parametre ile belirtilen arabirime bir işaretçi alır.

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

## <a name="classfactoryrelease"></a><a name="release"></a>ClassFactory::Sürüm

Geçerli `ClassFactory` nesne için başvuru sayısını eriter.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, başarısızlığı açıklayan bir HRESULT.
