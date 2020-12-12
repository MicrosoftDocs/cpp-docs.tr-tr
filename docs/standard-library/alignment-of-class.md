---
description: 'Hakkında daha fazla bilgi edinin: alignment_of sınıfı'
title: alignment_of Sınıfı
ms.date: 12/11/2019
f1_keywords:
- type_traits/std::alignment_of
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
ms.openlocfilehash: 7e1eeafb259b71f24cb272c079cdb485bb8e1b4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163658"
---
# <a name="alignment_of-class"></a>alignment_of Sınıfı

Belirtilen türün hizalamasını alır. Bu yapı, açısından uygulanır [`alignof`](../cpp/alignment-cpp-declarations.md) . **`alignof`** Yalnızca bir hizalama değerini sorgulamak için ihtiyacınız olduğunda doğrudan ' i kullanın. `alignment_of`Bir integral sabitine ihtiyacınız olduğunda, örneğin etiket gönderimi yaparken kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür sorgusu, tür *Ty* değerinin hizalamasının değerini tutar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[`<type_traits>`](type-traits.md)\
[`aligned_storage` Sınıfı](aligned-storage-class.md)
