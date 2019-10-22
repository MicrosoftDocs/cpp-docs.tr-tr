---
title: underlying_type sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::underlying_type
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
ms.openlocfilehash: ea4768d78047112a7584ca49b0e4487fad55a970
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688836"
---
# <a name="underlying_type-class"></a>underlying_type sınıfı

Bir numaralandırma türü için temeldeki integral türünü üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>Parametreler

*T* \
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonunun `type` üye typedef 'i, *t bir* sabit listesi türü *olduğunda, her*bir bir tür, `type` hiçbir üye typedef yok.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
