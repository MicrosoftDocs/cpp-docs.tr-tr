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
ms.openlocfilehash: 9fed5bb31b077288495a78aefcbd8401b3520bb6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367222"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags Yapısı

[RuntimeClass](runtimeclass-class.md)örneğinin türünü içerir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <unsigned int flags>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>Parametreler

*bayraklar*<br/>
[RuntimeClassType Numaralandırma](runtimeclasstype-enumeration.md) değeri.

## <a name="members"></a>Üyeler

### <a name="public-constants"></a>Genel Sabitler

|Adı|Açıklama|
|----------|-----------------|
|[RuntimeClassFlags::value Sabiti](#value-constant)|[RuntimeClassType Numaralandırma](runtimeclasstype-enumeration.md) değeri içerir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`RuntimeClassFlags`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** implements.h

**Ad alanı:** Microsoft::WRL

## <a name="runtimeclassflagsvalue-constant"></a><a name="value-constant"></a>RuntimeClassFlags::değer Sabiti

[RuntimeClassType Numaralandırma](runtimeclasstype-enumeration.md) değeri içeren bir alan.

```cpp
static const unsigned int value = flags;
```
