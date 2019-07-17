---
title: is_aggregate sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_aggregate
helpviewer_keywords:
- is_aggregate
ms.openlocfilehash: 7d979d4e4019ada12b72fb563c0b969fffe2c12d
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268050"
---
# <a name="isaggregate-class"></a>is_aggregate sınıfı

Türü olarak işaretlenmiş bir sınıf türü olup olmadığını sınar `aggregate`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_aggregate;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *T* sınıf türü olarak işaretlenmiş `aggregate`, aksi takdirde false tutar. Varsa *T* bir sınıf türü tam bir tür olmalıdır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
