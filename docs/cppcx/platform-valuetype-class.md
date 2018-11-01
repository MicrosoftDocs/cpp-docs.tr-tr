---
title: Platform::ValueType sınıfı
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ValueType::ToString
helpviewer_keywords:
- Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
ms.openlocfilehash: 57fb089f0d9dc53ba8a65cef41e3341168ffea45
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596410"
---
# <a name="platformvaluetype-class"></a>Platform::ValueType sınıfı

Temel sınıf için değer türlerinin örnekleri.

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class ValueType : Object
```

## <a name="public-methods"></a>Genel yöntemler

|||
|-|-|
|[ValueType::ToString](#tostring)|Bir nesnenin dize gösterimini döndürür. Devralınan [Platform::Object](../cppcx/platform-object-class.md).|

### <a name="remarks"></a>Açıklamalar

ValueType sınıfı, değer türleri oluşturmak için kullanılır. ValueType temel üye var. nesneden elde edilir. Ancak, derleyici bu temel ValueType sınıfından türetilen türlerin üyelerinden ayırır. Bir değer türü kutulandığında, derleyici bu temel üyeler etkilenebilecek.

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** platformu

**Meta veri:** platform.winmd

## <a name="tostring"></a> ValueType::ToString yöntemi

Bir nesnenin dize gösterimini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
Platform::String ToString();
```

### <a name="return-value"></a>Dönüş Değeri

Değeri temsil eden Platform::String.

## <a name="see-also"></a>Ayrıca Bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)