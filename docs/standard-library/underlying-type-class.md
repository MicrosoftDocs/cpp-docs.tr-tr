---
title: underlying_type sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::underlying_type
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
ms.openlocfilehash: 23e5e9bc5406265f49fca2ed220c597cb32e2a9a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609709"
---
# <a name="underlyingtype-class"></a>underlying_type sınıfı

Bir numaralandırma türünün temel alınan integral türü üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

`type` Şablon sınıfının üye typedef adları arka plandaki Tamsayı türünde *T*, *T* bir numaralandırma türü, aksi takdirde hiçbir üye typedef yoktur `type`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
