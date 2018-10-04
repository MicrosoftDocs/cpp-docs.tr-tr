---
title: ClassFactory sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory
- module/Microsoft::WRL::ClassFactory::AddRef
- module/Microsoft::WRL::ClassFactory::ClassFactory
- module/Microsoft::WRL::ClassFactory::LockServer
- module/Microsoft::WRL::ClassFactory::QueryInterface
- module/Microsoft::WRL::ClassFactory::Release
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::ClassFactory class
- Microsoft::WRL::ClassFactory::AddRef method
- Microsoft::WRL::ClassFactory::ClassFactory, constructor
- Microsoft::WRL::ClassFactory::LockServer method
- Microsoft::WRL::ClassFactory::QueryInterface method
- Microsoft::WRL::ClassFactory::Release method
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9e3639bb9d6ca88862b3a2fb4367fc429a665287
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788675"
---
# <a name="classfactory-class"></a>ClassFactory Sınıfı

Temel işlevselliğini uygular `IClassFactory` arabirimi.

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
Sıfırıncı arabirim.

*I1*<br/>
İlk arabirim.

*I2*<br/>
İkinci arabirim.

## <a name="remarks"></a>Açıklamalar

Yazılımınız `ClassFactory` Fabrika kullanıcı tanımlı bir uygulama sağlamak için.

Aşağıdaki programlama deseni nasıl kullanılacağını gösteren [uygular](../windows/implements-structure.md) yapısı üzerinde bir sınıf üreteci üçten fazla arabirimleri belirtin.

`struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                        | Açıklama
------------------------------------------- | -----------
[ClassFactory::ClassFactory](#classfactory) |

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                            | Açıklama
----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------
[ClassFactory::AddRef](#addref)                 | Geçerli başvuru sayısını artırır `ClassFactory` nesne.
[ClassFactory::LockServer](#lockserver)         | Artırır veya azaltır temel sayısını nesneleri geçerli tarafından izlenen `ClassFactory` nesne.
[ClassFactory::QueryInterface](#queryinterface) | Parametresi tarafından belirtilen arabirim işaretçisi alır.
[ClassFactory::Release](#release)               | Başvuru için geçerli sayısını azaltır `ClassFactory` nesne.

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

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="addref"></a>ClassFactory::AddRef

Geçerli başvuru sayısını artırır `ClassFactory` nesne.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

## <a name="classfactory"></a>ClassFactory::ClassFactory

```cpp
WRL_NOTHROW ClassFactory();
```

## <a name="lockserver"></a>ClassFactory::LockServer

Artırır veya azaltır temel sayısını nesneleri geçerli tarafından izlenen `ClassFactory` nesne.

```cpp
STDMETHOD(
   LockServer
)(BOOL fLock);
```

### <a name="parameters"></a>Parametreler

*fLock*<br/>
`true` izlenen nesne sayısını artırmak için. `false` izlenen nesnelerin sayısını azaltmak için.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, E_FAIL.

### <a name="remarks"></a>Açıklamalar

`ClassFactory` temel alınan örneği nesneleri izler [Modülü](../windows/module-class.md) sınıfı.

## <a name="queryinterface"></a>ClassFactory::QueryInterface

Parametresi tarafından belirtilen arabirim işaretçisi alır.

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

## <a name="release"></a>ClassFactory::Release

Başvuru için geçerli sayısını azaltır `ClassFactory` nesne.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.
