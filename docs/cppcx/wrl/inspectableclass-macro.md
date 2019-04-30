---
title: InspectableClass Makrosu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: 9d194f5a87ac4a142301bc896cb3ed172f119473
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398205"
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