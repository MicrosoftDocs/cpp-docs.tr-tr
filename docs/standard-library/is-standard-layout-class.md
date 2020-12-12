---
description: 'Hakkında daha fazla bilgi edinin: is_standard_layout sınıfı'
title: is_standard_layout Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_standard_layout
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
ms.openlocfilehash: 8f1f24fcb29e862dff10c2a51d1c9d0b2b28541f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271258"
---
# <a name="is_standard_layout-class"></a>is_standard_layout Sınıfı

Türün standart bir düzen olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_standard_layout;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür

## <a name="remarks"></a>Açıklamalar

Tür *Ty* , bellekteki üye nesnelerinin standart düzenine sahip bir sınıfdaysa, bu tür koşuldaki bir örnek true, aksi takdirde false barındırır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
