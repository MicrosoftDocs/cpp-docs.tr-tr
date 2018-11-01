---
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
ms.openlocfilehash: 74ae72dc87d45abba04d15303ed2ec92b18f8c28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668539"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags Yapısı

Örneğinin türünü içeren bir [RuntimeClass](../windows/runtimeclass-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <unsigned int flags>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>Parametreler

*bayrakları*<br/>
A [RuntimeClassType numaralandırması](../windows/runtimeclasstype-enumeration.md) değeri.

## <a name="members"></a>Üyeler

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[RuntimeClassFlags::value Sabiti](#value-constant)|İçeren bir [RuntimeClassType numaralandırması](../windows/runtimeclasstype-enumeration.md) değeri.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`RuntimeClassFlags`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="value-constant"></a>RuntimeClassFlags::value sabiti

İçeren bir alanda bir [RuntimeClassType numaralandırması](../windows/runtimeclasstype-enumeration.md) değeri.

```cpp
static const unsigned int value = flags;
```
