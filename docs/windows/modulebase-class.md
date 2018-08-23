---
title: ModuleBase sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
dev_langs:
- C++
helpviewer_keywords:
- ModuleBase class
ms.assetid: edce7591-6893-46f7-94a7-382827775548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e6d60e5114d189ddede87899bb55fba25a296c57
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601477"
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

|Ad|Açıklama|
|----------|-----------------|
|[ModuleBase::ModuleBase Oluşturucusu](../windows/modulebase-modulebase-constructor.md)|Bir örneğini başlatır `Module` sınıfı.|
|[ModuleBase::~ModuleBase Yıkıcısı](../windows/modulebase-tilde-modulebase-destructor.md)|Geçerli örneğinin başlatmasını geri alır `Module` sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ModuleBase::DecrementObjectCount Metodu](../windows/modulebase-decrementobjectcount-method.md)|Uygulandığında, azaltır nesne sayısını modülü tarafından izlenir.|
|[ModuleBase::IncrementObjectCount Metodu](../windows/modulebase-incrementobjectcount-method.md)|Uygulandığında, modül tarafından izlenen nesne sayısını artırır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ModuleBase`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)