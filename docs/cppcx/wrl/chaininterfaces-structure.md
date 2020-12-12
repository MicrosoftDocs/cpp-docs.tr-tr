---
description: 'Daha fazla bilgi edinin: ChainInterfaces yapısı'
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
ms.openlocfilehash: cc943b16d587a3b542e49d72e6bdc24ba2546e16
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328878"
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces Yapısı

Bir arabirim kimliği kümesine uygulanabilen doğrulama ve başlatma işlevlerini belirtir.

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
Istenir Arabirim KIMLIĞI 0.

*I1*<br/>
Istenir Arabirim KIMLIĞI 1.

*I2*<br/>
Seçim Arabirim KIMLIĞI 2.

*I3*<br/>
Seçim Arabirim KIMLIĞI 3.

*I4*<br/>
Seçim Arabirim KIMLIĞI 4.

*I5*<br/>
Seçim Arabirim KIMLIĞI 5.

*I6*<br/>
Seçim Arabirim KIMLIĞI 6.

*I7*<br/>
Seçim Arabirim KIMLIĞI 7.

*I8*<br/>
Seçim Arabirim KIMLIĞI 8.

*I9*<br/>
Seçim Arabirim KIMLIĞI 9.

*DerivedType*<br/>
Türetilmiş bir tür.

*BaseType*<br/>
Türetilmiş türün temel türü.

*hasImplements*<br/>
Bir Boolean değeri, bir **`true`** [Mixin](mixin-structure.md) yapısını [uygulayan](implements-structure.md) bir sınıf ile birlikte kullanamazsınız.

## <a name="members"></a>Üyeler

### <a name="protected-methods"></a>Korumalı Yöntemler

Ad                                                   | Açıklama
------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ChainInterfaces:: Canroto](#cancastto)               | Belirtilen arabirim KIMLIĞININ, şablon parametreleri tarafından tanımlanan tüm uzmanlıklarıyla düzenlenip yayınlanamayacağını gösterir `ChainInterface` .
[ChainInterfaces:: Rotounknown](#casttounknown)       | *I0* şablon parametresi tarafından tanımlanan türün arabirim işaretçisini öğesine bir işaretçiye yayınlar `IUnknown` .
[ChainInterfaces:: Fillarraywithııd](#fillarraywithiid) | *I0* şablon parametresi tarafından tanımlanan arabirim kimliğini belirtilen arabirim kimlikleri dizisinde belirtilen bir konuma depolar.
[ChainInterfaces:: Verify](#verify)                     | *I0* ile *I9* arasında şablon parametreleri tarafından tanımlanan her arabirimin `IUnknown` , ve/veya devraldığını doğrular `IInspectable` ve *I0* *I1* ile *I9* arasında devralır.

### <a name="protected-constants"></a>Korunan sabitler

Ad                                   | Açıklama
-------------------------------------- | -----------------------------------------------------------------------------------------------------------------
[ChainInterfaces:: ııdcount](#iidcount) | *I0* *aracılığıyla şablon* parametreleri tarafından belirtilen arabirimlerde bulunan arabirim kimliklerinin toplam sayısı.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`I0`

`ChainInterfaces`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL

## <a name="chaininterfacescancastto"></a><a name="cancastto"></a> ChainInterfaces:: Canroto

Belirtilen arabirim KIMLIĞININ varsayılan olmayan şablon parametreleri tarafından tanımlanan uzmanlıklerdeki her birine tür ataması yapılıp yapılmayacağını belirtir.

```cpp
__forceinline bool CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parametreler

*riıd*<br/>
Arabirim KIMLIĞI.

*PPV*<br/>
Başarılı bir şekilde saçıldığı son arabirim KIMLIĞINE yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** tüm atama işlemleri başarılı olursa; Aksi takdirde, **`false`** .

## <a name="chaininterfacescasttounknown"></a><a name="casttounknown"></a> ChainInterfaces:: Rotounknown

*I0* şablon parametresi tarafından tanımlanan türün arabirim işaretçisini öğesine bir işaretçiye yayınlar `IUnknown` .

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçisi `IUnknown` .

## <a name="chaininterfacesfillarraywithiid"></a><a name="fillarraywithiid"></a> ChainInterfaces:: Fillarraywithııd

*I0* şablon parametresi tarafından tanımlanan arabirim kimliğini belirtilen arabirim kimlikleri dizisinde belirtilen bir konuma depolar.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parametreler

*indeks*<br/>
*IIDS* dizisine bir dizin değeri işaretçisi.

*IID*<br/>
Arabirim kimlikleri dizisi.

## <a name="chaininterfacesiidcount"></a><a name="iidcount"></a> ChainInterfaces:: ııdcount

*I0* *aracılığıyla şablon* parametreleri tarafından belirtilen arabirimlerde bulunan arabirim kimliklerinin toplam sayısı.

```cpp
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;
```

### <a name="return-value"></a>Dönüş Değeri

Toplam arabirim kimliği sayısı.

### <a name="remarks"></a>Açıklamalar

*I0* ve *I1* şablon parametreleri gerekir ve *I2* ile *I9* arasındaki parametreler isteğe bağlıdır. Her arabirimin IID sayısı genellikle 1 ' dir.

## <a name="chaininterfacesverify"></a><a name="verify"></a> ChainInterfaces:: Verify

*I0* ile *I9* arasında şablon parametreleri tarafından tanımlanan her arabirimin `IUnknown` , ve/veya devraldığını doğrular `IInspectable` ve *I0* *I1* ile *I9* arasında devralır.

```cpp
WRL_NOTHROW __forceinline static void Verify();
```

### <a name="remarks"></a>Açıklamalar

Doğrulama işlemi başarısız olursa, hatayı **`static_assert`** açıklayan bir hata mesajı yayar.

*I0* ve *I1* şablon parametreleri gerekir ve *I2* ile *I9* arasındaki parametreler isteğe bağlıdır.
