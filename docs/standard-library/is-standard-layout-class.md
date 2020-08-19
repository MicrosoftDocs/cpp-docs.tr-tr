---
title: is_standard_layout Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_standard_layout
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
ms.openlocfilehash: fba77be22796f3cb5495543d262dd270ac13d598
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560601"
---
# <a name="is_standard_layout-class"></a>is_standard_layout Sınıfı

Türün standart bir düzen olup olmadığını sınar.

## <a name="syntax"></a>Söz dizimi

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
