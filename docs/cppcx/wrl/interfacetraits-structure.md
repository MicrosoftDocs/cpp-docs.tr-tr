---
title: InterfaceTraits Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
- implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid
- implements/Microsoft::WRL::Details::InterfaceTraits::IidCount
- implements/Microsoft::WRL::Details::InterfaceTraits::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::InterfaceTraits structure
- Microsoft::WRL::Details::InterfaceTraits::CanCastTo method
- Microsoft::WRL::Details::InterfaceTraits::CastToBase method
- Microsoft::WRL::Details::InterfaceTraits::CastToUnknown method
- Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid method
- Microsoft::WRL::Details::InterfaceTraits::IidCount constant
- Microsoft::WRL::Details::InterfaceTraits::Verify method
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
ms.openlocfilehash: 17f743a38af3ddc600a55e38905d19868d076a22
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371364"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename I0>
struct __declspec(novtable) InterfaceTraits;

template<typename CloakedType>
struct __declspec(novtable) InterfaceTraits<
    CloakedIid<CloakedType>
>;

template<>
struct __declspec(novtable) InterfaceTraits<Nil>;
```

### <a name="parameters"></a>Parametreler

*I0*<br/>
Arabirimin adı.

*Gizlenmiş Tip*<br/>
Desteklenen `RuntimeClass` `Implements` arabirim iI'leri listesinde olmayacak bir arabirim için. `ChainInterfaces`

## <a name="remarks"></a>Açıklamalar

Arabirimin ortak özelliklerini uygular.

İkinci şablon, gizlenmiş arabirimler için bir uzmanlık alanıdır. Üçüncü şablon, Nil parametreleri için bir uzmanlık alanıdır.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a><a name="public-typedefs"></a>Genel Typedefs

Adı   | Açıklama
------ | ------------------------------------------
`Base` | *I0* şablon parametresi ile eş anlamlıdır.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                                   | Açıklama
------------------------------------------------------ | ----------------------------------------------------------------------------------------
[Arayüz Özellikleri::Cancastto](#cancastto)               | Belirtilen işaretçinin bir işaretçiye `Base`atılıp atılmayacağını gösterir.
[Arayüz Özellikleri::Casttobase](#casttobase)             | Belirtilen işaretçiyi bir işaretçiye `Base`atar.
[Arayüz Özellikleri::Casttounknown](#casttounknown)       | Belirtilen işaretçiyi bir işaretçiye `IUnknown`atar.
[ArayüzÖzellikleri::FillArrayWithIid](#fillarraywithiid) | Dizin bağımsız değişkeni tarafından belirtilen dizi öğesinin arabirim kimliğini `Base` atar.
[Arayüz Özellikleri::Doğrula](#verify)                     | Doğrulanmış `Base` doğrular.

### <a name="public-constants"></a>Genel Sabitler

Adı                                   | Açıklama
-------------------------------------- | ---------------------------------------------------------------------------------------
[ArayüzÖzellikleri::IidCount](#iidcount) | Geçerli `InterfaceTraits` nesneyle ilişkili arabirim işlemi numarasını tutar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`InterfaceTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** implements.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="interfacetraitscancastto"></a><a name="cancastto"></a>Arayüz Özellikleri::Cancastto

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
template<typename T>
static __forceinline bool CanCastTo(
   _In_ T* ptr,
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parametreler

*Ptr*<br/>
Bir tür için işaretçi adı.

*Riid*<br/>
Arayüz `Base`kimliği.

*Ppv*<br/>
Bu işlem başarılı olursa, *ppv* tarafından `Base`belirtilen arabirime işaret ediyor. Aksi *takdirde, ppv* `nullptr`ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

bu işlem başarılı olursa ve *ptr* bir `Base`işaretçiye atılırsa **doğrudur;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Belirtilen işaretçinin bir işaretçiye `Base`atılıp atılmayacağını gösterir.

Hakkında daha `Base`fazla bilgi için [Public Typedefs](#public-typedefs) bölümüne bakın.

## <a name="interfacetraitscasttobase"></a><a name="casttobase"></a>Arayüz Özellikleri::Casttobase

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
template<typename T>
static __forceinline Base* CastToBase(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Parametre *ptr*türü .

*Ptr*<br/>
*T*türüne işaretçi .

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `Base`.

### <a name="remarks"></a>Açıklamalar

Belirtilen işaretçiyi bir işaretçiye `Base`atar.

Hakkında daha `Base`fazla bilgi için [Public Typedefs](#public-typedefs) bölümüne bakın.

## <a name="interfacetraitscasttounknown"></a><a name="casttounknown"></a>Arayüz Özellikleri::Casttounknown

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
template<typename T>
static __forceinline IUnknown* CastToUnknown(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Parametre *ptr*türü .

*Ptr*<br/>
*T*yazın işaretçisi .

### <a name="return-value"></a>Dönüş Değeri

Türetildiği IUnknown `Base` işaretçisi.

### <a name="remarks"></a>Açıklamalar

Belirtilen işaretçiyi bir işaretçiye `IUnknown`atar.

Hakkında daha `Base`fazla bilgi için [Public Typedefs](#public-typedefs) bölümüne bakın.

## <a name="interfacetraitsfillarraywithiid"></a><a name="fillarraywithiid"></a>ArayüzÖzellikleri::FillArrayWithIid

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parametreler

*Dizin*<br/>
Sıfır tabanlı dizin değeri içeren bir alana işaretçi.

*iids*<br/>
Bir dizi arayüz tonu.

### <a name="remarks"></a>Açıklamalar

Dizin bağımsız değişkeni tarafından belirtilen dizi öğesinin arabirim kimliğini `Base` atar.

Bu API'nin adının aksine, yalnızca bir dizi öğesi değiştirilir; tüm dizi değil.

Hakkında daha `Base`fazla bilgi için [Public Typedefs](#public-typedefs) bölümüne bakın.

## <a name="interfacetraitsiidcount"></a><a name="iidcount"></a>ArayüzÖzellikleri::IidCount

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
static const unsigned long IidCount = 1;
```

### <a name="remarks"></a>Açıklamalar

Geçerli `InterfaceTraits` nesneyle ilişkili arabirim işlemi numarasını tutar.

## <a name="interfacetraitsverify"></a><a name="verify"></a>Arayüz Özellikleri::Doğrula

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
__forceinline static void Verify();
```

### <a name="remarks"></a>Açıklamalar

Doğrulanmış `Base` doğrular.

Hakkında daha `Base`fazla bilgi için [Public Typedefs](#public-typedefs) bölümüne bakın.
