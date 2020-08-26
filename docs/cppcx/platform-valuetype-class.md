---
title: 'Platform:: ValueType sınıfı'
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ValueType::ToString
helpviewer_keywords:
- Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
ms.openlocfilehash: f4ce34fa3f197424833d34bdb866712d412e69c3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846556"
---
# <a name="platformvaluetype-class"></a>Platform:: ValueType sınıfı

Değer türlerinin örnekleri için temel sınıf.

## <a name="syntax"></a>Syntax

```cpp
public ref class ValueType : Object
```

## <a name="public-methods"></a>Ortak Yöntemler

| Ad | Açıklama |
|--|--|
| [ValueType:: ToString](#tostring) | Nesnenin dize gösterimini döndürür. [Platform:: nesnesinden](../cppcx/platform-object-class.md)devralındı. |

### <a name="remarks"></a>Açıklamalar

ValueType sınıfı değer türlerini oluşturmak için kullanılır. ValueType, temel üyeleri olan nesnesinden türetilir. Ancak derleyici, bu temel üyeleri ValueType sınıfından türetilmiş değer türlerinden ayırır. Derleyici, bir değer türü kutulandığında bu temel üyeleri yeniden ekler.

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Meta veri:** platform. winmd

## <a name="valuetypetostring-method"></a><a name="tostring"></a> ValueType:: ToString yöntemi

Nesnenin dize gösterimini döndürür.

### <a name="syntax"></a>Syntax

```cpp
Platform::String ToString();
```

### <a name="return-value"></a>Dönüş Değeri

Değeri temsil eden platform:: String.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
