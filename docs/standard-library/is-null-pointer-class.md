---
title: is_null_pointer sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_null_pointer
helpviewer_keywords:
- is_null_pointer
ms.assetid: f3b3601b-f162-4803-a6e9-dabf5c3876cc
ms.openlocfilehash: 10979e790cb1f3e1ae3eace4f88a0328cb9a7f01
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480398"
---
# <a name="isnullpointer-class"></a>is_null_pointer sınıfı

Std::nullptr_t türü olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_null_pointer;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *T* olduğu `std::nullptr_t`, aksi takdirde false tutar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
