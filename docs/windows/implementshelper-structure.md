---
title: Implementshelper yapısı | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper
- implements/Microsoft::WRL::Details::ImplementsHelper::CanCastTo
- implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
- implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
- implements/Microsoft::WRL::Details::ImplementsHelper::IidCount
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::ImplementsHelper structure
- Microsoft::WRL::Details::ImplementsHelper::CanCastTo method
- Microsoft::WRL::Details::ImplementsHelper::CastToUnknown method
- Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid method
- Microsoft::WRL::Details::ImplementsHelper::IidCount constant
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d734e98d8d7713451be1a16e08e58676f2b0cde4
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163692"
---
# <a name="implementshelper-structure"></a>ImplementsHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename RuntimeClassFlagsT, typename ILst, bool IsDelegateToClass>
friend struct Details::ImplementsHelper;
```

### <a name="parameters"></a>Parametreler

*RuntimeClassFlagsT*<br/>
Bir veya daha fazla belirten bayraklar alanı [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırıcılar.

*ILst*<br/>
Arabirim kimlikleri listesi.

*IsDelegateToClass*<br/>
Belirtin **true** varsa geçerli örneğini `Implements` ilk arabirim kimliği taban sınıfıdır *ILst*; Aksi takdirde **false**.

## <a name="remarks"></a>Açıklamalar

Uygulama yardımcı [uygular](../windows/implements-structure.md) yapısı.

Bu şablon, arabirimin bir listeyi dikkatle inceler ve temel sınıflar ve etkinleştirmek gereken bilgileri ekler `QueryInterface`.

## <a name="members"></a>Üyeler

### <a name="protected-methods"></a>Korumalı Yöntemler

Ad                                                    | Açıklama
------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------
[Implementshelper::cancastto](#cancastto)               | Belirtilen arabirim kimliği için bir işaretçi alır
[Implementshelper::casttounknown](#casttounknown)       | Temel alınan bir işaretçi alır `IUnknown` arabirimi için geçerli `Implements` yapısı.
[Implementshelper::fillarraywithıid](#fillarraywithiid) | Belirtilen bir dizi öğesine geçerli sıfırıncı şablon parametresi tarafından belirtilen arabirim kimliği ekler.
[Implementshelper::ıidcount](#iidcount)                 | Uygulanan arabirimi kimliği geçerli sayısını tutar `Implements` nesne.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ImplementsHelper`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="cancastto"></a>Implementshelper::cancastto

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

*riid*<br/>
Başvuru için bir arabirim kimliği.

*ppv*<br/>
Bu işlem başarılı olursa, arabirim işaretçisi tarafından belirtilen *riid* veya *IID*.

*IID*<br/>
Başvuru için bir arabirim kimliği.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Belirtilen arabirim kimliği için bir işaretçi alır

## <a name="casttounknown"></a>Implementshelper::casttounknown

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Dönüş Değeri

Temel işaretçisinin `IUnknown` arabirimi.

### <a name="remarks"></a>Açıklamalar

Temel alınan bir işaretçi alır `IUnknown` arabirimi için geçerli `Implements` yapısı.

## <a name="fillarraywithiid"></a>Implementshelper::fillarraywithıid

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
void FillArrayWithIid(
   _Inout_ unsigned long *index,
   _Inout_ IID* iids) throw();
```

### <a name="parameters"></a>Parametreler

*Dizin*<br/>
Bu işlem için başlangıç dizi öğesini gösteren sıfır tabanlı dizini. Bu işlem tamamlandığında *dizin* 1 azaltılır.

*IID'leri*<br/>
IID'leri türünde bir dizi.

### <a name="remarks"></a>Açıklamalar

Belirtilen bir dizi öğesine geçerli sıfırıncı şablon parametresi tarafından belirtilen arabirim kimliği ekler.

## <a name="iidcount"></a>Implementshelper::ıidcount

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
static const unsigned long IidCount;
```

### <a name="remarks"></a>Açıklamalar

Uygulanan arabirimi kimliği geçerli sayısını tutar `Implements` nesne.
