---
title: alignment_of Sınıfı
ms.date: 12/11/2019
f1_keywords:
- type_traits/std::alignment_of
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
ms.openlocfilehash: d241848edf57fe4876c35e22f1762abf5d6888fa
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302321"
---
# <a name="alignment_of-class"></a>alignment_of Sınıfı

Belirtilen türün hizalamasını alır. Bu yapı, [Hizalama](../cpp/alignment-cpp-declarations.md)bakımından uygulanır. Yalnızca bir hizalama değerini sorgulamak **istediğinizde doğrudan hizalamasını** kullanın. Bir integral sabitine ihtiyaç duyduğunuzda alignment_of kullanın, örneğin, etiket gönderme.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>Parametreler

*Ty*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür sorgusu, tür *Ty*değerinin hizalamasının değerini tutar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[aligned_storage Sınıfı](../standard-library/aligned-storage-class.md)
