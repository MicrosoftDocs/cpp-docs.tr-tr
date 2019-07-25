---
title: alignment_of Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::alignment_of
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
ms.openlocfilehash: 5222e70965db69d33ec62039bf9013a52d145705
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456445"
---
# <a name="alignmentof-class"></a>alignment_of Sınıfı

Belirtilen türün hizalamasını alır. Bu yapı, [Hizalama](../cpp/alignof-and-alignas-cpp.md)bakımından uygulanır. Yalnızca `alignof` bir hizalama değerini sorgulamak için ihtiyacınız olduğunda doğrudan ' i kullanın. Bir integral sabitine ihtiyacınız olduğunda, örneğin etiket gönderimi yaparken alignment_of kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür sorgusu, tür *Ty*değerinin hizalamasının değerini tutar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[aligned_storage Sınıfı](../standard-library/aligned-storage-class.md)
