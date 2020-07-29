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
ms.openlocfilehash: d7908670b67df7dbf7b2b74e98f8b59cf30f8e96
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87184949"
---
# <a name="implementshelper-structure"></a>ImplementsHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <typename RuntimeClassFlagsT, typename ILst, bool IsDelegateToClass>
friend struct Details::ImplementsHelper;
```

### <a name="parameters"></a>Parametreler

*RuntimeClassFlagsT*<br/>
Bir veya daha fazla [RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırıcıları belirten bayrakların alanı.

*ILst*<br/>
Arabirim kimliklerinin listesi.

*IsDelegateToClass*<br/>
**`true`** Geçerli örneğinin `Implements` *ILst*içindeki ilk arabirim kimliğine ait bir temel sınıf olup olmadığını belirtin; Aksi takdirde, **`false`** .

## <a name="remarks"></a>Açıklamalar

, [Uygulayan](implements-structure.md) yapıyı uygulamaya yardımcı olur.

Bu şablon bir arabirim listesini inceler ve bunları temel sınıflar olarak ve etkinleştirilmesi gereken bilgileri olarak ekler `QueryInterface` .

## <a name="members"></a>Üyeler

### <a name="protected-methods"></a>Korumalı Yöntemler

Ad                                                    | Açıklama
------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------
[ImplementsHelper:: Canroto](#cancastto)               | Belirtilen arabirim KIMLIĞINE bir işaretçi alır.
[ImplementsHelper:: Rotounknown](#casttounknown)       | Geçerli yapı için temel alınan arabirime yönelik bir işaretçi alır `IUnknown` `Implements` .
[ImplementsHelper:: Fillarraywithııd](#fillarraywithiid) | Belirtilen dizi öğesine geçerli bir diğer şablon parametresi tarafından belirtilen arabirim KIMLIĞINI ekler.
[ImplementsHelper:: ııdcount](#iidcount)                 | Geçerli nesnedeki uygulanan arabirim kimliklerinin sayısını tutar `Implements` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ImplementsHelper`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="implementshelpercancastto"></a><a name="cancastto"></a>ImplementsHelper:: Canroto

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

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

*riıd*<br/>
Arabirim KIMLIĞINE başvuru.

*PPV*<br/>
Bu işlem başarılı olursa, *riıd* veya *IID*tarafından belirtilen arabirime yönelik bir işaretçi.

*'si*<br/>
Arabirim KIMLIĞINE başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Belirtilen arabirim KIMLIĞINE bir işaretçi alır.

## <a name="implementshelpercasttounknown"></a><a name="casttounknown"></a>ImplementsHelper:: Rotounknown

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan arabirime yönelik işaretçi `IUnknown` .

### <a name="remarks"></a>Açıklamalar

Geçerli yapı için temel alınan arabirime yönelik bir işaretçi alır `IUnknown` `Implements` .

## <a name="implementshelperfillarraywithiid"></a><a name="fillarraywithiid"></a>ImplementsHelper:: Fillarraywithııd

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
void FillArrayWithIid(
   _Inout_ unsigned long *index,
   _Inout_ IID* iids) throw();
```

### <a name="parameters"></a>Parametreler

*indeks*<br/>
Bu işlem için başlangıç dizisi öğesini gösteren sıfır tabanlı bir dizin. Bu işlem tamamlandığında, *Dizin* 1 artırılır.

*IID*<br/>
IIDS türünde bir dizi.

### <a name="remarks"></a>Açıklamalar

Belirtilen dizi öğesine geçerli bir diğer şablon parametresi tarafından belirtilen arabirim KIMLIĞINI ekler.

## <a name="implementshelperiidcount"></a><a name="iidcount"></a>ImplementsHelper:: ııdcount

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
static const unsigned long IidCount;
```

### <a name="remarks"></a>Açıklamalar

Geçerli nesnedeki uygulanan arabirim kimliklerinin sayısını tutar `Implements` .
