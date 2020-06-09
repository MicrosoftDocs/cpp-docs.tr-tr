---
title: alignment_of Sınıfı
ms.date: 12/11/2019
f1_keywords:
- type_traits/std::alignment_of
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
ms.openlocfilehash: c2af00ac32b3013820a3109783c4bf7eb42ec445
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623724"
---
# <a name="alignment_of-class"></a>alignment_of Sınıfı

Belirtilen türün hizalamasını alır. Bu yapı, [Hizalama](../cpp/alignment-cpp-declarations.md)bakımından uygulanır. Yalnızca bir hizalama değerini sorgulamak **istediğinizde doğrudan hizalamasını** kullanın. Bir integral sabitine ihtiyaç duyduğunuzda alignment_of kullanın, örneğin, etiket gönderme.

## <a name="syntax"></a>Söz dizimi

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

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](type-traits.md)\
[aligned_storage sınıfı](aligned-storage-class.md)
