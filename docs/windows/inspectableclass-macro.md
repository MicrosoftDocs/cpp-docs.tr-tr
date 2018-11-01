---
title: InspectableClass Makrosu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: 55d5aed96ff7c8b01142f8d4de81a431fdfcc2d5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631601"
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
Aşağıdakilerden birini [TrustLevel](https://msdn.microsoft.com/library/br224625.aspx) numaralandırılmış değerlerinin.

## <a name="remarks"></a>Açıklamalar

**Inspectableclass** makrosu, yalnızca Windows çalışma zamanı türleri ile kullanılabilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[RuntimeClass Sınıfı](../windows/runtimeclass-class.md)