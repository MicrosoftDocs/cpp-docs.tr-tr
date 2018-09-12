---
title: RuntimeClassFlags yapısı | Microsoft Docs
ms.custom: ''
ms.date: 09/07/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
- implements/Microsoft::WRL::RuntimeClassFlags::value
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::RuntimeClassFlags structure
- Microsoft::WRL::RuntimeClassFlags::value constant
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6c3cb141576598aa39c718316048900622c4df41
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691464"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags Yapısı

Örneğinin türünü içeren bir [RuntimeClass](../windows/runtimeclass-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   unsigned int flags
>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>Parametreler

*bayrakları*  
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
