---
title: ModuleBase sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::~ModuleBase
dev_langs:
- C++
helpviewer_keywords:
- ModuleBase class
- Microsoft::WRL::Details::ModuleBase::DecrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::IncrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::ModuleBase, constructor
- Microsoft::WRL::Details::ModuleBase::~ModuleBase, destructor
ms.assetid: edce7591-6893-46f7-94a7-382827775548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a87b5d617663e87e8c69596e6b1eedca61996b80
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169560"
---
# <a name="modulebase-class"></a>ModuleBase Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
class ModuleBase;
```

## <a name="remarks"></a>Açıklamalar

Temel sınıfını temsil eden [Modülü](../windows/module-class.md) sınıfları.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                         | Açıklama
-------------------------------------------- | ---------------------------------------------------------
[ModuleBase::ModuleBase](#modulebase)        | Bir örneğini başlatır `Module` sınıfı.
[ModuleBase:: ~ ModuleBase](#tilde-modulebase) | Geçerli örneğinin başlatmasını geri alır `Module` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                      | Açıklama
--------------------------------------------------------- | -------------------------------------------------------------------------
[ModuleBase::DecrementObjectCount](#decrementobjectcount) | Uygulandığında, azaltır nesne sayısını modülü tarafından izlenir.
[Modulebase::ıncrementobjectcount](#incrementobjectcount) | Uygulandığında, modül tarafından izlenen nesne sayısını artırır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ModuleBase`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="tilde-modulebase"></a>ModuleBase:: ~ ModuleBase

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
virtual ~ModuleBase();
```

### <a name="remarks"></a>Açıklamalar

Geçerli örneğinin başlatmasını geri alır `ModuleBase` sınıfı.

## <a name="decrementobjectcount"></a>ModuleBase::DecrementObjectCount

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
virtual long DecrementObjectCount() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Azaltma işleminden önce sayısı.

### <a name="remarks"></a>Açıklamalar

Uygulandığında, azaltır nesne sayısını modülü tarafından izlenir.

## <a name="incrementobjectcount"></a>Modulebase::ıncrementobjectcount

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
virtual long IncrementObjectCount() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Önce Artım işlemi sayısı.

### <a name="remarks"></a>Açıklamalar

Uygulandığında, modül tarafından izlenen nesne sayısını artırır.

## <a name="modulebase"></a>ModuleBase::ModuleBase

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
ModuleBase();
```

### <a name="remarks"></a>Açıklamalar

Bir örneğini başlatır `Module` sınıfı.
