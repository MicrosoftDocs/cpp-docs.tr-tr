---
title: InspectableClass Makrosu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: ee2a76edb967923a03ce6720b4163baf1cc48c32
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500483"
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

**Uzayına** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[RuntimeClass Sınıfı](runtimeclass-class.md)