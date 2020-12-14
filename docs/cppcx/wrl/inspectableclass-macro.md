---
description: ': InspectableClass makrosu hakkında daha fazla bilgi edinin'
title: InspectableClass Makrosu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: cb19db7f35e7bda351cd84fa4dcf1f6a2b2ea2ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229008"
---
# <a name="inspectableclass-macro"></a>InspectableClass Makrosu

Çalışma zamanı sınıf adı ve güven düzeyini ayarlar.

## <a name="syntax"></a>Sözdizimi

```cpp
InspectableClass(
   runtimeClassName,
   trustLevel)
```

### <a name="parameters"></a>Parametreler

*runtimeClassName*<br/>
Çalışma zamanı sınıfının tam metin adı.

*trustLevel*<br/>
[TrustLevel](/windows/win32/api/inspectable/ne-inspectable-trustlevel) numaralandırılmış değerlerden biri.

## <a name="remarks"></a>Açıklamalar

**InspectableClass** makrosu yalnızca Windows çalışma zamanı türleriyle kullanılabilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[RuntimeClass Sınıfı](runtimeclass-class.md)
