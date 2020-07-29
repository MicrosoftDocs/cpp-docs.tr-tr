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
ms.openlocfilehash: bbf20e2269e6d62206e06e748174d7b88898cd68
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87198105"
---
# <a name="classfactory-class"></a>ClassFactory Sınıfı

, Arabiriminin temel işlevlerini uygular `IClassFactory` .

## <a name="syntax"></a>Söz dizimi

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
Diğer arabirim.

*I1*<br/>
İlk arabirim.

*I2*<br/>
İkinci arabirim.

## <a name="remarks"></a>Açıklamalar

`ClassFactory`Kullanıcı tanımlı bir fabrika uygulamasını sağlamak için kullanın.

Aşağıdaki programlama modelinde, bir sınıf fabrikasında üçten fazla arabirim belirtmek için [uygulayan](implements-structure.md) yapının nasıl kullanılacağı gösterilmektedir.

`struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                        | Açıklama
------------------------------------------- | -----------
[ClassFactory:: ClassFactory](#classfactory) |

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                            | Açıklama
----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------
[ClassFactory:: AddRef](#addref)                 | Geçerli nesne için başvuru sayısını artırır `ClassFactory` .
[ClassFactory:: LockServer](#lockserver)         | Geçerli nesne tarafından izlenen temeldeki nesne sayısını artırır veya azaltır `ClassFactory` .
[ClassFactory:: QueryInterface](#queryinterface) | Parametreye göre belirtilen arabirime bir işaretçi alır.
[ClassFactory:: Release](#release)               | Geçerli nesne için başvuru sayısını azaltır `ClassFactory` .

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

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL

## <a name="classfactoryaddref"></a><a name="addref"></a>ClassFactory:: AddRef

Geçerli nesne için başvuru sayısını artırır `ClassFactory` .

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

## <a name="classfactoryclassfactory"></a><a name="classfactory"></a>ClassFactory:: ClassFactory

```cpp
WRL_NOTHROW ClassFactory();
```

## <a name="classfactorylockserver"></a><a name="lockserver"></a>ClassFactory:: LockServer

Geçerli nesne tarafından izlenen temeldeki nesne sayısını artırır veya azaltır `ClassFactory` .

```cpp
STDMETHOD(
   LockServer
)(BOOL fLock);
```

### <a name="parameters"></a>Parametreler

*fLock*<br/>
**`true`** izlenen nesne sayısını artırmak için. **`false`** izlenen nesne sayısını azaltmak için.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, E_FAIL.

### <a name="remarks"></a>Açıklamalar

`ClassFactory`[Modül](module-class.md) sınıfının temel bir örneğindeki nesneleri izler.

## <a name="classfactoryqueryinterface"></a><a name="queryinterface"></a>ClassFactory:: QueryInterface

Parametreye göre belirtilen arabirime bir işaretçi alır.

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Parametreler

*riıd*<br/>
Arabirim KIMLIĞI.

*ppvObject*<br/>
Bu işlem tamamlandığında, parametre *riıd*tarafından belirtilen arabirime yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

## <a name="classfactoryrelease"></a><a name="release"></a>ClassFactory:: Release

Geçerli nesne için başvuru sayısını azaltır `ClassFactory` .

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.
