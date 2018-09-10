---
title: Platform::delegate sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Delegate
dev_langs:
- C++
helpviewer_keywords:
- Platform::Delegate Class
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78ac7cce43dbe08097c1e7b78423fadafc7f5309
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44101917"
---
# <a name="platformdelegate-class"></a>Platform::delegate sınıfı

Bir işlev nesnesi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
public delegate void delegate_name();
```

### <a name="members"></a>Üyeler

GetHashCode(), üzerine yaz temsilci sınıfında ve ToString() yöntemleri türetilen [Platform::Object sınıfı](../cppcx/platform-object-class.md).

### <a name="remarks"></a>Açıklamalar

Kullanma [temsilci](../windows/delegate-cpp-component-extensions.md) ; temsilci oluşturmak için anahtar sözcüğü Platform::Delegate açıkça kullanmayın. Daha fazla bilgi için [Temsilciler](../cppcx/delegates-c-cx.md). Bir temsilci oluşturup ilişkin bir örnek için bkz: [C++'ta Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** platformu

**Meta veri:** platform.winmd

## <a name="see-also"></a>Ayrıca Bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)