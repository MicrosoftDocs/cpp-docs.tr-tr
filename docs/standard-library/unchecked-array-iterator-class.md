---
title: unchecked_array_iterator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- stdext::unchecked_array_iterator
ms.assetid: 693b3b30-4e3a-465b-be06-409700bc50b1
ms.openlocfilehash: 5344a108f32b694b9dafac78dbb8eb7064cdf4cc
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455003"
---
# <a name="uncheckedarrayiterator-class"></a>unchecked_array_iterator Sınıfı

Sınıfı `unchecked_array_iterator` , bir diziyi veya işaretçiyi işaretsiz bir yineleyiciye kaydırasağlar. Bu uyarıları genel olarak susturmak yerine bu sınıfı ham işaretçiler veya diziler için bir sarmalayıcı olarak ( [make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator) işlevini kullanarak), işaretlenmeyen işaretçi uyarılarını yönetmek için hedeflenmiş bir yol olarak kullanın. Mümkünse, bu [checked_array_iterator](../standard-library/checked-array-iterator-class.md)sınıfının denetlenen sürümünü tercih edin.

> [!NOTE]
> Bu sınıf, C++ standart kitaplığın Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Iterator>
class unchecked_array_iterator;
```

## <a name="remarks"></a>Açıklamalar

Bu sınıf, [stdext](../standard-library/stdext-namespace.md) ad alanında tanımlanır.

Bu, [Checked_array_iterator sınıfının](../standard-library/checked-array-iterator-class.md) denetlenmeyen sürümüdür ve tüm aynı aşırı yüklemeleri ve üyeleri destekler. Denetlenen Yineleyici özelliği kod örnekleriyle ilgili daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<Yineleyici >

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
