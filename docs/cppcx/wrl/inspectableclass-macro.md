---
title: InspectableClass Makrosu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: 9d194f5a87ac4a142301bc896cb3ed172f119473
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025717"
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
Aşağıdakilerden birini [TrustLevel](/windows/desktop/api/inspectable/ne-inspectable-trustlevel) numaralandırılmış değerlerinin.

## <a name="remarks"></a>Açıklamalar

**Inspectableclass** makrosu, yalnızca Windows çalışma zamanı türleri ile kullanılabilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca bkz.

[RuntimeClass Sınıfı](runtimeclass-class.md)