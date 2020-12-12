---
description: 'Hakkında daha fazla bilgi edinin: underlying_type sınıfı'
title: underlying_type sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::underlying_type
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
ms.openlocfilehash: e717abe854f13fc96926deba1d4bf177529618cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132710"
---
# <a name="underlying_type-class"></a>underlying_type sınıfı

Bir numaralandırma türü için temeldeki integral türünü üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

`type`Sınıf şablonunun üye typedef 'i, t bir sabit listesi türü olduğunda, bu *t*'in  temeldeki integral türünü, aksi takdirde hiç üye typedef yok `type` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
