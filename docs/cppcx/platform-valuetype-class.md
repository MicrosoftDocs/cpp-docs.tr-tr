---
description: 'Daha fazla bilgi edinin: Platform:: ValueType sınıfı'
title: 'Platform:: ValueType sınıfı'
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ValueType::ToString
helpviewer_keywords:
- Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
ms.openlocfilehash: e6873b4b884586d06dae6e2fd1966041fd49bcc8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307814"
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
