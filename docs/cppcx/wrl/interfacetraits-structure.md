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
ms.openlocfilehash: e8222ccaca9572331412b90e696829568eedcf8e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58787754"
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
Bir arabirimin adı.

*CloakedType*<br/>
İçin `RuntimeClass`, `Implements` ve `ChainInterfaces`, arabirim kimlikleri listesinde olmayacak bir arabirim desteklenir.

## <a name="remarks"></a>Açıklamalar

Genel özelliklerini bir arabirim uygular.

İkinci bir özelleştirmesi gizlenmiş arabirimleri için şablonudur. Nil parametreleri için bir özelleştirmesi üçüncü şablonudur.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

Ad   | Açıklama
------ | ------------------------------------------
`Base` | İçin bir eşanlamlı *I0* şablon parametresi.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                   | Açıklama
------------------------------------------------------ | ----------------------------------------------------------------------------------------
[Interfacetraits::cancastto](#cancastto)               | Belirtilen işaretçi işaretçisi içerip içermeyeceğini belirten `Base`.
[Interfacetraits::casttobase](#casttobase)             | Belirtilen bir işaretçi işaretçisi bıraktığı `Base`.
[Interfacetraits::casttounknown](#casttounknown)       | Belirtilen bir işaretçi işaretçisi bıraktığı `IUnknown`.
[Interfacetraits::fillarraywithıid](#fillarraywithiid) | Arabirim kimliği atar `Base` dizini bağımsız değişkeni tarafından belirtilen dizi öğesi için.
[Interfacetraits::Verify](#verify)                     | Doğrular `Base` düzgün şekilde türetilir.

### <a name="public-constants"></a>Genel sabitler

Ad                                   | Açıklama
-------------------------------------- | ---------------------------------------------------------------------------------------
[Interfacetraits::ıidcount](#iidcount) | Geçerli ile ilişkili kimlikleri arabirimi sayısını tutar `InterfaceTraits` nesne.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`InterfaceTraits`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="cancastto"></a>Interfacetraits::cancastto

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
Bir tür için bir işaretçi adı.

*riid*<br/>
Arabirim Kimliği `Base`.

*ppv*<br/>
Bu işlem başarılı olursa *ppv* tarafından belirtilen arabirim işaret `Base`. Aksi takdirde, *ppv* ayarlanır `nullptr`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** bu işlem başarılı olursa ve *ptr* işaretçisine dönüştürme `Base`; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Belirtilen işaretçi işaretçisi içerip içermeyeceğini belirten `Base`.

Hakkında daha fazla bilgi için `Base`, bkz: [genel Typedefler](#public-typedefs) bölümü.

## <a name="casttobase"></a>Interfacetraits::casttobase

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
template<typename T>
static __forceinline Base* CastToBase(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Parametresinin türü *ptr*.

*ptr*<br/>
Bir tür işaretçisi *T*.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `Base`.

### <a name="remarks"></a>Açıklamalar

Belirtilen bir işaretçi işaretçisi bıraktığı `Base`.

Hakkında daha fazla bilgi için `Base`, bkz: [genel Typedefler](#public-typedefs) bölümü.

## <a name="casttounknown"></a>Interfacetraits::casttounknown

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
template<typename T>
static __forceinline IUnknown* CastToUnknown(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Parametresinin türü *ptr*.

*ptr*<br/>
İşaretçi türüne *T*.

### <a name="return-value"></a>Dönüş Değeri

IUnknown işaretçisi içinden `Base` türetilir.

### <a name="remarks"></a>Açıklamalar

Belirtilen bir işaretçi işaretçisi bıraktığı `IUnknown`.

Hakkında daha fazla bilgi için `Base`, bkz: [genel Typedefler](#public-typedefs) bölümü.

## <a name="fillarraywithiid"></a>Interfacetraits::fillarraywithıid

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parametreler

*Dizin*<br/>
Sıfır tabanlı dizin değeri içeren bir alan için işaretçi.

*IID'leri*<br/>
Arabirim kimlikleri dizisi.

### <a name="remarks"></a>Açıklamalar

Arabirim kimliği atar `Base` dizini bağımsız değişkeni tarafından belirtilen dizi öğesi için.

Bu API adını aykırı, yalnızca bir dizi öğesi değiştirildi; Tüm dizi değildir.

Hakkında daha fazla bilgi için `Base`, bkz: [genel Typedefler](#public-typedefs) bölümü.

## <a name="iidcount"></a>Interfacetraits::ıidcount

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
static const unsigned long IidCount = 1;
```

### <a name="remarks"></a>Açıklamalar

Geçerli ile ilişkili kimlikleri arabirimi sayısını tutar `InterfaceTraits` nesne.

## <a name="verify"></a>Interfacetraits::Verify

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
__forceinline static void Verify();
```

### <a name="remarks"></a>Açıklamalar

Doğrular `Base` düzgün şekilde türetilir.

Hakkında daha fazla bilgi için `Base`, bkz: [genel Typedefler](#public-typedefs) bölümü.
