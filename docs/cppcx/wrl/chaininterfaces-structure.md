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
ms.openlocfilehash: dd1af3fb5c1079a40d8248dc71ae4972537aa856
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372662"
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces Yapısı

Arabirim kimlikleri kümesine uygulanabilecek doğrulama ve başlatma işlevlerini belirtir.

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
(Gerekli) Arayüz Kimliği 0.

*I1*<br/>
(Gerekli) Arayüz Kimliği 1.

*I2*<br/>
(İsteğe bağlı) Arayüz Kimliği 2.

*I3*<br/>
(İsteğe bağlı) Arayüz Kimliği 3.

*I4*<br/>
(İsteğe bağlı) Arayüz Kimliği 4.

*I5*<br/>
(İsteğe bağlı) Arayüz Kimliği 5.

*I6*<br/>
(İsteğe bağlı) Arayüz Kimliği 6.

*I7*<br/>
(İsteğe bağlı) Arayüz Kimliği 7.

*I8*<br/>
(İsteğe bağlı) Arayüz Kimliği 8.

*I9*<br/>
(İsteğe bağlı) Arayüz Kimliği 9.

*Türemiş Tür*<br/>
Türemiş bir tür.

*BaseType*<br/>
Türemiş bir türün taban türü.

*hasImplements*<br/>
Boolean değeri, **eğer doğruysa,** [Uygular](implements-structure.md) sıva türetilmiştir olmayan bir sınıf ile [mixin](mixin-structure.md) yapısı kullanamazsınız anlamına gelir.

## <a name="members"></a>Üyeler

### <a name="protected-methods"></a>Korumalı Yöntemler

Adı                                                   | Açıklama
------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ChainInterfaces::CanCastTo](#cancastto)               | Belirtilen arabirim kimliğinin şablon parametreleri tarafından tanımlanan uzmanlıkların `ChainInterface` her birine atılıp atılmayacağını gösterir.
[ChainInterfaces::CastToUnknown](#casttounknown)       | *I0* şablon parametresi tarafından tanımlanan türdeki arabirim işaretçisini bir işaretçiye `IUnknown`atar.
[ChainInterfaces::FillArrayWithIid](#fillarraywithiid) | *I0* şablon parametresi tarafından tanımlanan arabirim kimliğini belirli bir arabirim kimlikleri dizisinde belirli bir konuma saklar.
[ChainInterfaces::Doğrula](#verify)                     | *Şablon parametreleri i0* ile I9 tarafından tanımlanan `IUnknown` her arabirimin `IInspectable` *i1'den* *I0* *I9'a* devrolduğunu ve/veya devraldığı doğrular. *I9*

### <a name="protected-constants"></a>Korumalı Sabitler

Adı                                   | Açıklama
-------------------------------------- | -----------------------------------------------------------------------------------------------------------------
[ChainInterfaces::IidCount](#iidcount) | Şablon parametreleri *I0* ile *I9*tarafından belirtilen arabirimlerde bulunan toplam arabirim numarası.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`I0`

`ChainInterfaces`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** implements.h

**Ad alanı:** Microsoft::WRL

## <a name="chaininterfacescancastto"></a><a name="cancastto"></a>ChainInterfaces::CanCastTo

Belirtilen arabirim kimliğinin varsayılan olmayan şablon parametreleri tarafından tanımlanan uzmanlıkların her birine atılıp atılmayacağını gösterir.

```cpp
__forceinline bool CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parametreler

*Riid*<br/>
Arayüz kimliği.

*Ppv*<br/>
Başarıyla atan son arabirim kimliğine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

tüm döküm işlemleri başarılı olsaydı **doğrudur;** aksi takdirde, **yanlış**.

## <a name="chaininterfacescasttounknown"></a><a name="casttounknown"></a>ChainInterfaces::CastToUnknown

*I0* şablon parametresi tarafından tanımlanan türdeki arabirim işaretçisini bir işaretçiye `IUnknown`atar.

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `IUnknown`.

## <a name="chaininterfacesfillarraywithiid"></a><a name="fillarraywithiid"></a>ChainInterfaces::FillArrayWithIid

*I0* şablon parametresi tarafından tanımlanan arabirim kimliğini belirli bir arabirim kimlikleri dizisinde belirli bir konuma saklar.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parametreler

*Dizin*<br/>
*Iids* dizisinde bir dizin değeri işaretçisi.

*iids*<br/>
Bir dizi arayüz tonu.

## <a name="chaininterfacesiidcount"></a><a name="iidcount"></a>ChainInterfaces::IidCount

Şablon parametreleri *I0* ile *I9*tarafından belirtilen arabirimlerde bulunan toplam arabirim numarası.

```cpp
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;
```

### <a name="return-value"></a>Dönüş Değeri

Arabirim tayının toplam sayısı.

### <a name="remarks"></a>Açıklamalar

Şablon *parametreleri I0* ve *I1* gereklidir ve *I2* ile *I9* parametreleri isteğe bağlıdır. Her arabirimin IID sayısı genellikle 1'dir.

## <a name="chaininterfacesverify"></a><a name="verify"></a>ChainInterfaces::Doğrula

*Şablon parametreleri i0* ile I9 tarafından tanımlanan `IUnknown` her arabirimin `IInspectable` *i1'den* *I0* *I9'a* devrolduğunu ve/veya devraldığı doğrular. *I9*

```cpp
WRL_NOTHROW __forceinline static void Verify();
```

### <a name="remarks"></a>Açıklamalar

Doğrulama işlemi başarısız olursa, hatayı açıklayan bir `static_assert` hata iletisi yayır.

Şablon *parametreleri I0* ve *I1* gereklidir ve *I2* ile *I9* parametreleri isteğe bağlıdır.
