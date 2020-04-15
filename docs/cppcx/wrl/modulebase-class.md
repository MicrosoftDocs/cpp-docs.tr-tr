---
title: ModuleBase Sınıfı
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::~ModuleBase
helpviewer_keywords:
- ModuleBase class
- Microsoft::WRL::Details::ModuleBase::DecrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::IncrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::ModuleBase, constructor
- Microsoft::WRL::Details::ModuleBase::~ModuleBase, destructor
ms.assetid: edce7591-6893-46f7-94a7-382827775548
ms.openlocfilehash: 13a8ceef3133e9946524e1fcd02e96535eccd7fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371268"
---
# <a name="modulebase-class"></a>ModuleBase Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
class ModuleBase;
```

## <a name="remarks"></a>Açıklamalar

[Modül](module-class.md) sınıflarının taban sınıfını temsil eder.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                         | Açıklama
-------------------------------------------- | ---------------------------------------------------------
[ModuleBase::ModuleBase](#modulebase)        | `Module` sınıfının örneğini başlatır.
[ModuleBase::~ModuleBase](#tilde-modulebase) | Sınıfın geçerli örneğini `Module` deinitialize eder.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                                      | Açıklama
--------------------------------------------------------- | -------------------------------------------------------------------------
[ModuleBase::DecrementObjectCount](#decrementobjectcount) | Uygulandığında, modül tarafından izlenen nesnelerin sayısını azat eder.
[ModuleBase::ArtışNesne Sayısı](#incrementobjectcount) | Uygulandığında, modül tarafından izlenen nesnelerin sayısını n itimat eder.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ModuleBase`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** implements.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="modulebasemodulebase"></a><a name="tilde-modulebase"></a>ModuleBase::~ModuleBase

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
virtual ~ModuleBase();
```

### <a name="remarks"></a>Açıklamalar

Sınıfın geçerli örneğini `ModuleBase` deinitialize eder.

## <a name="modulebasedecrementobjectcount"></a><a name="decrementobjectcount"></a>ModuleBase::DecrementObjectCount

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
virtual long DecrementObjectCount() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kararname işleminden önceki sayım.

### <a name="remarks"></a>Açıklamalar

Uygulandığında, modül tarafından izlenen nesnelerin sayısını azat eder.

## <a name="modulebaseincrementobjectcount"></a><a name="incrementobjectcount"></a>ModuleBase::ArtışNesne Sayısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
virtual long IncrementObjectCount() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Artış işleminden önceki sayım.

### <a name="remarks"></a>Açıklamalar

Uygulandığında, modül tarafından izlenen nesnelerin sayısını n itimat eder.

## <a name="modulebasemodulebase"></a><a name="modulebase"></a>ModuleBase::ModuleBase

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
ModuleBase();
```

### <a name="remarks"></a>Açıklamalar

`Module` sınıfının örneğini başlatır.
