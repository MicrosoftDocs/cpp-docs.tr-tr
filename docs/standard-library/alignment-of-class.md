---
title: alignment_of Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::alignment_of
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
ms.openlocfilehash: 2633749a72ceeea197579dca4300b58250f60d73
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604423"
---
# <a name="alignmentof-class"></a>alignment_of Sınıfı

Belirtilen tür hizalamasını alır. Bu struct açısından uygulanan [alignof](../cpp/alignof-and-alignas-cpp.md). Kullanım `alignof` doğrudan yalnızca gerektiğinde bir hizalama değeri sorgulanamıyor. Etiket dağıtım yaparken örneği için bir tamsayı sabiti gerektiğinde alignment_of kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Türü bir sorgu türü hizalamasını değerini tutan *Ty*.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[aligned_storage Sınıfı](../standard-library/aligned-storage-class.md)<br/>
