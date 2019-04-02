---
title: ComPtrRefBase Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
- client/Microsoft::WRL::Details::ComPtrRefBase::ptr_
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRefBase class
- Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable** operator
- Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown** operator
- Microsoft::WRL::Details::ComPtrRefBase::ptr_ data member
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
ms.openlocfilehash: df4e2aa1ce650fd5b1f04baf2f7c4cd2fb4cff93
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787806"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
class ComPtrRefBase;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
A [ComPtr\<T >](comptr-class.md) türü veya tür, kesmenin tarafından temsil edilen arabirim sınıfından türetilen `ComPtr`.

## <a name="remarks"></a>Açıklamalar

Temel sınıfı temsil eder [ComPtrRef](comptrref-class.md) sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

Ad            | Açıklama
--------------- | -------------------------------------------------
`InterfaceType` | Şablon parametresinin türü için bir eşanlamlı *T*.

### <a name="public-operators"></a>Ortak İşleçler

Ad                                                                       | Açıklama
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[ComPtrRefBase::operator Iınspectable **](#operator-iinspectable-star-star) | Geçerli bıraktığı [ptr_](#ptr) veri üyesi için bir işaretçi-için-a-işaretçi- `IInspectable` arabirimi.
[ComPtrRefBase::operator IUnknown **](#operator-iunknown-star-star)         | Geçerli bıraktığı [ptr_](#ptr) veri üyesi için bir işaretçi-için-a-işaretçi- `IUnknown` arabirimi.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                        | Açıklama
--------------------------- | ----------------------------------------------------------------
[ComPtrRefBase::ptr_](#ptr) | Geçerli bir şablon parametresi tarafından belirtilen tür işaretçisi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtrRefBase`

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::wrl:: details

## <a name="operator-iinspectable-star-star"></a>ComPtrRefBase::operator Iınspectable\* \* işleci

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>Açıklamalar

Geçerli bıraktığı [ptr_](#ptr) veri üyesi için bir işaretçi-için-a-işaretçi- `IInspectable` arabirimi.

Bir hata varsa yayıldığını geçerli `ComPtrRefBase` öğesinden türetilen değil `IInspectable`.

Bu tür dönüştürme kullanılabilir yalnızca `__WRL_CLASSIC_COM__` tanımlanır.

## <a name="operator-iunknown-star-star"></a>ComPtrRefBase::operator IUnknown ** işleci

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>Açıklamalar

Geçerli bıraktığı [ptr_](#ptr) veri üyesi için bir işaretçi-için-a-işaretçi- `IUnknown` arabirimi.

Bir hata varsa yayıldığını geçerli `ComPtrRefBase` öğesinden türetilen değil `IUnknown`.

## <a name="ptr"></a>ComPtrRefBase::ptr_

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
T* ptr_;
```

### <a name="remarks"></a>Açıklamalar

Geçerli bir şablon parametresi tarafından belirtilen tür işaretçisi. `ptr_` korunan verilerin üyesidir.