---
title: ImplementsHelper Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper
- implements/Microsoft::WRL::Details::ImplementsHelper::CanCastTo
- implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
- implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
- implements/Microsoft::WRL::Details::ImplementsHelper::IidCount
helpviewer_keywords:
- Microsoft::WRL::Details::ImplementsHelper structure
- Microsoft::WRL::Details::ImplementsHelper::CanCastTo method
- Microsoft::WRL::Details::ImplementsHelper::CastToUnknown method
- Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid method
- Microsoft::WRL::Details::ImplementsHelper::IidCount constant
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
ms.openlocfilehash: e33842f574df5617fb40c5b3f6bb8324d5ba7c1e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371393"
---
# <a name="implementshelper-structure"></a>ImplementsHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename RuntimeClassFlagsT, typename ILst, bool IsDelegateToClass>
friend struct Details::ImplementsHelper;
```

### <a name="parameters"></a>Parametreler

*RuntimeClassFlagsT*<br/>
Bir veya daha fazla [RuntimeClassType](runtimeclasstype-enumeration.md) sayıtaycı belirten bir bayrak alanı.

*ILst*<br/>
Arabirim tümleri listesi.

*IsdelegatetoClass*<br/>
Geçerli örneği *ILst'teki*ilk arabirim kimliğinin taban `Implements` sınıfıysa **doğru** belirtin; aksi takdirde, **yanlış**.

## <a name="remarks"></a>Açıklamalar

[Uygular](implements-structure.md) yapısının uygulanmasına yardımcı olur.

Bu şablon arabirimler listesini dolaşır ve bunları temel sınıflar olarak ve `QueryInterface`etkinleştirmek için gerekli olan bilgiler olarak ekler.

## <a name="members"></a>Üyeler

### <a name="protected-methods"></a>Korumalı Yöntemler

Adı                                                    | Açıklama
------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------
[UygularHelper::CanCastTo](#cancastto)               | Belirtilen arabirim kimliğiiçin bir işaretçi alır.
[UygularHelper::CastToUnknown](#casttounknown)       | Geçerli `Implements` yapı için `IUnknown` temel arabirim için bir işaretçi alır.
[UygularHelper::FillArrayWithIid](#fillarraywithiid) | Geçerli sıfırth şablon parametresi tarafından belirtilen arabirim kimliğini belirtilen dizi öğesine ekler.
[UygularHelper::IidCount](#iidcount)                 | Geçerli `Implements` nesnede uygulanan arabirim dislerinin sayısını tutar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ImplementsHelper`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** implements.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="implementshelpercancastto"></a><a name="cancastto"></a>UygularHelper::CanCastTo

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);

HRESULT CanCastTo(
   _In_ const IID &iid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parametreler

*Riid*<br/>
Arabirim kimliğine başvuru.

*Ppv*<br/>
Bu işlem başarılı olursa, *riid* veya *iid*tarafından belirtilen arabirimin işaretçisi.

*ııd*<br/>
Arabirim kimliğine başvuru.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Belirtilen arabirim kimliğiiçin bir işaretçi alır.

## <a name="implementshelpercasttounknown"></a><a name="casttounknown"></a>UygularHelper::CastToUnknown

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Dönüş Değeri

Temel `IUnknown` arabirimi işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçerli `Implements` yapı için `IUnknown` temel arabirim için bir işaretçi alır.

## <a name="implementshelperfillarraywithiid"></a><a name="fillarraywithiid"></a>UygularHelper::FillArrayWithIid

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
void FillArrayWithIid(
   _Inout_ unsigned long *index,
   _Inout_ IID* iids) throw();
```

### <a name="parameters"></a>Parametreler

*Dizin*<br/>
Bu işlem için başlangıç dizi öğesini gösteren sıfır tabanlı dizin. Bu işlem tamamlandığında, *dizin* 1 ile artımlanır.

*iids*<br/>
Bir dizi tür iids.

### <a name="remarks"></a>Açıklamalar

Geçerli sıfırth şablon parametresi tarafından belirtilen arabirim kimliğini belirtilen dizi öğesine ekler.

## <a name="implementshelperiidcount"></a><a name="iidcount"></a>UygularHelper::IidCount

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
static const unsigned long IidCount;
```

### <a name="remarks"></a>Açıklamalar

Geçerli `Implements` nesnede uygulanan arabirim dislerinin sayısını tutar.
