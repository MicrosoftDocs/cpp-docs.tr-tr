---
description: 'Daha fazla bilgi edinin: ınterfacetoyits yapısı'
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
ms.openlocfilehash: 8dfa540119b0a120ea7b8d9365a0e8b8203939b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124533"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

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

*CloakedType*<br/>
`RuntimeClass`Ve için `Implements` `ChainInterfaces` , desteklenen arabirim kimlikleri listesinde olmayan bir arabirim.

## <a name="remarks"></a>Açıklamalar

Bir arabirimin ortak karakteristiklerini uygular.

İkinci şablon, örtülmüş arabirimler için bir özelleştirme. Üçüncü şablon, Nil parametreleri için bir özelleştirme.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a><a name="public-typedefs"></a> Ortak tür tanımları

Ad   | Açıklama
------ | ------------------------------------------
`Base` | *I0* şablon parametresi için bir eş anlamlı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                   | Açıklama
------------------------------------------------------ | ----------------------------------------------------------------------------------------
[Interfacetoyits:: Cankıto](#cancastto)               | Belirtilen işaretçinin işaretçisine bir işaretçiye tür ataması yapılıp yapılmayacağını belirtir `Base` .
[Interfacetoyits:: Rotobase](#casttobase)             | Belirtilen işaretçiyi işaretçisine çevirir `Base` .
[Interfacetoyits:: Rotounknown](#casttounknown)       | Belirtilen işaretçiyi işaretçisine çevirir `IUnknown` .
[InterfaceTraits:: Fillarraywithııd](#fillarraywithiid) | Öğesinin arabirim KIMLIĞINI `Base` Dizin bağımsız değişkeni tarafından belirtilen dizi öğesine atar.
[Interfacetoyits:: doğrula](#verify)                     | `Base`Doğru şekilde türetildiğini doğrular.

### <a name="public-constants"></a>Genel sabitler

Ad                                   | Açıklama
-------------------------------------- | ---------------------------------------------------------------------------------------
[Interfacetoyits:: ııdcount](#iidcount) | Geçerli nesneyle ilişkili arabirim kimliklerinin sayısını tutar `InterfaceTraits` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`InterfaceTraits`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="interfacetraitscancastto"></a><a name="cancastto"></a> Interfacetoyits:: Cankıto

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
template<typename T>
static __forceinline bool CanCastTo(
   _In_ T* ptr,
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parametreler

*ptr*<br/>
Bir tür işaretçisinin adı.

*riıd*<br/>
Öğesinin arabirim KIMLIĞI `Base` .

*PPV*<br/>
Bu işlem başarılı olursa, *PPV* tarafından belirtilen arabirime işaret eder `Base` . Aksi halde, *PPV* olarak ayarlanır **`nullptr`** .

### <a name="return-value"></a>Dönüş Değeri

**`true`** Bu işlem başarılı olursa ve *PTR* , öğesine bir işaretçiye tür, `Base` Aksi durumda, **`false`** .

### <a name="remarks"></a>Açıklamalar

Belirtilen işaretçinin işaretçisine bir işaretçiye tür ataması yapılıp yapılmayacağını belirtir `Base` .

Hakkında daha fazla bilgi için `Base` bkz. [Public Typedefs](#public-typedefs) bölümü.

## <a name="interfacetraitscasttobase"></a><a name="casttobase"></a> Interfacetoyits:: Rotobase

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
template<typename T>
static __forceinline Base* CastToBase(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
*PTR* parametresinin türü.

*ptr*<br/>
*T* türü işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçisi `Base` .

### <a name="remarks"></a>Açıklamalar

Belirtilen işaretçiyi işaretçisine çevirir `Base` .

Hakkında daha fazla bilgi için `Base` bkz. [Public Typedefs](#public-typedefs) bölümü.

## <a name="interfacetraitscasttounknown"></a><a name="casttounknown"></a> Interfacetoyits:: Rotounknown

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
template<typename T>
static __forceinline IUnknown* CastToUnknown(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
*PTR* parametresinin türü.

*ptr*<br/>
*T* türü işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Türetilen IUnknown için işaretçi `Base` .

### <a name="remarks"></a>Açıklamalar

Belirtilen işaretçiyi işaretçisine çevirir `IUnknown` .

Hakkında daha fazla bilgi için `Base` bkz. [Public Typedefs](#public-typedefs) bölümü.

## <a name="interfacetraitsfillarraywithiid"></a><a name="fillarraywithiid"></a> InterfaceTraits:: Fillarraywithııd

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parametreler

*indeks*<br/>
Sıfır tabanlı bir dizin değeri içeren bir alana yönelik işaretçi.

*IID*<br/>
Arabirim kimlikleri dizisi.

### <a name="remarks"></a>Açıklamalar

Öğesinin arabirim KIMLIĞINI `Base` Dizin bağımsız değişkeni tarafından belirtilen dizi öğesine atar.

Bu API 'nin adı tersine, yalnızca bir dizi öğesi değiştirilir; tüm dizi değildir.

Hakkında daha fazla bilgi için `Base` bkz. [Public Typedefs](#public-typedefs) bölümü.

## <a name="interfacetraitsiidcount"></a><a name="iidcount"></a> Interfacetoyits:: ııdcount

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
static const unsigned long IidCount = 1;
```

### <a name="remarks"></a>Açıklamalar

Geçerli nesneyle ilişkili arabirim kimliklerinin sayısını tutar `InterfaceTraits` .

## <a name="interfacetraitsverify"></a><a name="verify"></a> Interfacetoyits:: doğrula

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
__forceinline static void Verify();
```

### <a name="remarks"></a>Açıklamalar

`Base`Doğru şekilde türetildiğini doğrular.

Hakkında daha fazla bilgi için `Base` bkz. [Public Typedefs](#public-typedefs) bölümü.
