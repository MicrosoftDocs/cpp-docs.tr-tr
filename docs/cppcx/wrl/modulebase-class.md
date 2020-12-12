---
description: 'Daha fazla bilgi edinin: ModuleBase sınıfı'
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
ms.openlocfilehash: 6540068cee62da5d1a9039a15bcb5bd53ff3aea2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186252"
---
# <a name="modulebase-class"></a>ModuleBase Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Syntax

```cpp
class ModuleBase;
```

## <a name="remarks"></a>Açıklamalar

[Modül](module-class.md) sınıflarının taban sınıfını temsil eder.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                         | Açıklama
-------------------------------------------- | ---------------------------------------------------------
[ModuleBase:: ModuleBase](#modulebase)        | `Module` sınıfının örneğini başlatır.
[ModuleBase:: ~ ModuleBase](#tilde-modulebase) | Sınıfın geçerli örneğini kaldırır `Module` .

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                      | Açıklama
--------------------------------------------------------- | -------------------------------------------------------------------------
[ModuleBase::D ecrementObjectCount](#decrementobjectcount) | Uygulandığında, modül tarafından izlenen nesne sayısını azaltır.
[ModuleBase:: IncrementObjectCount](#incrementobjectcount) | Uygulandığında, modül tarafından izlenen nesne sayısını artırır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ModuleBase`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="modulebasemodulebase"></a><a name="tilde-modulebase"></a> ModuleBase:: ~ ModuleBase

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
virtual ~ModuleBase();
```

### <a name="remarks"></a>Açıklamalar

Sınıfın geçerli örneğini kaldırır `ModuleBase` .

## <a name="modulebasedecrementobjectcount"></a><a name="decrementobjectcount"></a> ModuleBase::D ecrementObjectCount

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
virtual long DecrementObjectCount() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Azaltma işleminden önceki sayı.

### <a name="remarks"></a>Açıklamalar

Uygulandığında, modül tarafından izlenen nesne sayısını azaltır.

## <a name="modulebaseincrementobjectcount"></a><a name="incrementobjectcount"></a> ModuleBase:: IncrementObjectCount

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
virtual long IncrementObjectCount() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Artış işleminden önceki sayı.

### <a name="remarks"></a>Açıklamalar

Uygulandığında, modül tarafından izlenen nesne sayısını artırır.

## <a name="modulebasemodulebase"></a><a name="modulebase"></a> ModuleBase:: ModuleBase

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
ModuleBase();
```

### <a name="remarks"></a>Açıklamalar

`Module` sınıfının örneğini başlatır.
