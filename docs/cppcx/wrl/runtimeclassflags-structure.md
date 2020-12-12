---
description: 'Daha fazla bilgi edinin: RuntimeClassFlags yapısı'
title: RuntimeClassFlags Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
- implements/Microsoft::WRL::RuntimeClassFlags::value
helpviewer_keywords:
- Microsoft::WRL::RuntimeClassFlags structure
- Microsoft::WRL::RuntimeClassFlags::value constant
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
ms.openlocfilehash: 7874447fbbbe429884c5a79d0c70bb93e617ec61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209275"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags Yapısı

Bir [RuntimeClass](runtimeclass-class.md)örneği için türü içerir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <unsigned int flags>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>Parametreler

*bayraklar*<br/>
[RuntimeClassType numaralandırma](runtimeclasstype-enumeration.md) değeri.

## <a name="members"></a>Üyeler

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[RuntimeClassFlags::value Sabiti](#value-constant)|Bir [RuntimeClassType numaralandırma](runtimeclasstype-enumeration.md) değeri içerir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`RuntimeClassFlags`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL

## <a name="runtimeclassflagsvalue-constant"></a><a name="value-constant"></a> RuntimeClassFlags:: value sabiti

[RuntimeClassType numaralandırma](runtimeclasstype-enumeration.md) değeri içeren bir alan.

```cpp
static const unsigned int value = flags;
```
