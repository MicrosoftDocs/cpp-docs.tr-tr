---
title: ChainInterfaces Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
- implements/Microsoft::WRL::ChainInterfaces::CanCastTo
- implements/Microsoft::WRL::ChainInterfaces::CastToUnknown
- implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid
- implements/Microsoft::WRL::ChainInterfaces::IidCount
- implements/Microsoft::WRL::ChainInterfaces::Verify
helpviewer_keywords:
- Microsoft::WRL::ChainInterfaces structure
- Microsoft::WRL::ChainInterfaces::CanCastTo method
- Microsoft::WRL::ChainInterfaces::CastToUnknown method
- Microsoft::WRL::ChainInterfaces::FillArrayWithIid method
- Microsoft::WRL::ChainInterfaces::IidCount constant
- Microsoft::WRL::ChainInterfaces::Verify method
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
ms.openlocfilehash: 9fd315f017d3dcc9823054ea99e845ec99bc4192
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54334999"
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces Yapısı

Arabirim kimlikleri kümesine uygulanabilir doğrulama ve başlatma işlevleri belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    typename I0,
    typename I1,
    typename I2 = Details::Nil,
    typename I3 = Details::Nil,
    typename I4 = Details::Nil,
    typename I5 = Details::Nil,
    typename I6 = Details::Nil,
    typename I7 = Details::Nil,
    typename I8 = Details::Nil,
    typename I9 = Details::Nil
>
struct ChainInterfaces : I0;

template <
    typename DerivedType,
    typename BaseType,
    bool hasImplements,
    typename I1,
    typename I2,
    typename I3,
    typename I4,
    typename I5,
    typename I6,
    typename I7,
    typename I8,
    typename I9
>
struct ChainInterfaces<
    MixIn<
        DerivedType,
        BaseType,
        hasImplements
    >, I1, I2, I3, I4, I5, I6, I7, I8, I9
>;
```

### <a name="parameters"></a>Parametreler

*I0*<br/>
(Gerekli) Arabirim Kimliği: 0.

*I1*<br/>
(Gerekli) Arabirim kimliği 1.

*I2*<br/>
(İsteğe bağlı) Arabirim kimliği 2.

*I3*<br/>
(İsteğe bağlı) Arabirim Kimliği 3.

*I4*<br/>
(İsteğe bağlı) Arabirim Kimliği 4.

*I5*<br/>
(İsteğe bağlı) Arabirim kimliği 5.

*I6*<br/>
(İsteğe bağlı) Arabirim kimliği 6.

*I7*<br/>
(İsteğe bağlı) Arabirim kimliği 7.

*I8*<br/>
(İsteğe bağlı) 8 arabirim kimliği.

*I9*<br/>
(İsteğe bağlı) Arabirim Kimliği 9.

*DerivedType*<br/>
Türetilmiş bir tür.

*BaseType*<br/>
Türetilmiş türün temel türü.

*hasImplements*<br/>
Bir Boole değeri olması durumunda **true**, kullanamazsınız anlamına gelir. bir [MixIn](mixin-structure.md) türünden türemez bir sınıf ile yapı [uygular](implements-structure.md) yapıda.

## <a name="members"></a>Üyeler

### <a name="protected-methods"></a>Korumalı Yöntemler

Ad                                                   | Açıklama
------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[Chainınterfaces::cancastto](#cancastto)               | Her tarafından tanımlanan uzmanlıkları belirtilen arabirim kimliği içerip içermeyeceğini belirten `ChainInterface` şablon parametreleri.
[Chainınterfaces::casttounknown](#casttounknown)       | Arabirim işaretçisi tarafından tanımlanan tür yayınlar *I0* şablon parametresi için bir işaretçi olarak `IUnknown`.
[Chainınterfaces::fillarraywithıid](#fillarraywithiid) | Arabirim kimliği tarafından tanımlanan depoları *I0* şablon parametresi belirtilen bir dizisinde belirtilen bir konuma arabiriminin kimlikleri.
[Chainınterfaces::Verify](#verify)                     | Her arabirim şablon parametreleri tarafından tanımlanan doğrular *I0* aracılığıyla *I9* devraldığı `IUnknown` ve/veya `IInspectable`ve *I0* devralır *I1* aracılığıyla *I9*.

### <a name="protected-constants"></a>Korumalı sabitleri

Ad                                   | Açıklama
-------------------------------------- | -----------------------------------------------------------------------------------------------------------------
[Chainınterfaces::ıidcount](#iidcount) | Arabirim kimlikleri şablon parametreleri tarafından belirtilen arabirimlerden bulunan toplam sayısı *I0* aracılığıyla *I9*.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`I0`

`ChainInterfaces`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="cancastto"></a>Chainınterfaces::cancastto

Her varsayılan olmayan şablon parametreleri tarafından tanımlanan uzmanlıkları belirtilen arabirim kimliği içerip içermeyeceğini belirtir.

```cpp
__forceinline bool CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parametreler

*riid*<br/>
Bir arabirim kimliği.

*ppv*<br/>
Atama başarıyla son arabirim kimliği için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

**doğru** tüm atama işlemlerinin başarılı olduysa; Aksi takdirde, **false**.

## <a name="casttounknown"></a>Chainınterfaces::casttounknown

Arabirim işaretçisi tarafından tanımlanan tür yayınlar *I0* şablon parametresi için bir işaretçi olarak `IUnknown`.

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `IUnknown`.

## <a name="fillarraywithiid"></a>Chainınterfaces::fillarraywithıid

Arabirim kimliği tarafından tanımlanan depoları *I0* şablon parametresi belirtilen bir dizisinde belirtilen bir konuma arabiriminin kimlikleri.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parametreler

*Dizin*<br/>
Bir dizin değeri işaretçisine *IID'leri* dizisi.

*IID'leri*<br/>
Arabirim kimlikleri dizisi.

## <a name="iidcount"></a>Chainınterfaces::ıidcount

Arabirim kimlikleri şablon parametreleri tarafından belirtilen arabirimlerden bulunan toplam sayısı *I0* aracılığıyla *I9*.

```cpp
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;
```

### <a name="return-value"></a>Dönüş Değeri

Arabirim kimlikleri toplam sayısı.

### <a name="remarks"></a>Açıklamalar

Şablon parametreleri *I0* ve *I1* gereklidir ve parametreleri *I2* aracılığıyla *I9* isteğe bağlıdır. Genellikle her arabirim IID'si sayısı 1'dir.

## <a name="verify"></a>Chainınterfaces::Verify

Her arabirim şablon parametreleri tarafından tanımlanan doğrular *I0* aracılığıyla *I9* devraldığı `IUnknown` ve/veya `IInspectable`ve *I0* devralır *I1* aracılığıyla *I9*.

```cpp
WRL_NOTHROW __forceinline static void Verify();
```

### <a name="remarks"></a>Açıklamalar

Doğrulama işlemi başarısız olursa bir `static_assert` hatayı açıklayan bir hata iletisi gösterir.

Şablon parametreleri *I0* ve *I1* gereklidir ve parametreleri *I2* aracılığıyla *I9* isteğe bağlıdır.
