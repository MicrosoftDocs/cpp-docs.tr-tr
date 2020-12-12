---
description: 'Hakkında daha fazla bilgi edinin: unchecked_array_iterator sınıfı'
title: unchecked_array_iterator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- stdext::unchecked_array_iterator
ms.assetid: 693b3b30-4e3a-465b-be06-409700bc50b1
ms.openlocfilehash: 6f2bbe4c31a76101a04e8c5be6a4e0dcf67cf87e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132749"
---
# <a name="unchecked_array_iterator-class"></a>unchecked_array_iterator Sınıfı

`unchecked_array_iterator`Sınıfı, bir diziyi veya işaretçiyi işaretsiz bir yineleyiciye kaydırasağlar. Bu uyarıları genel olarak susturmak yerine bu sınıfı ham işaretçiler veya diziler için bir sarmalayıcı olarak ( [make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator) işlevi kullanılarak), işaretlenmemiş işaretçi uyarılarını yönetmek için hedeflenmiş bir yol olarak kullanın. Mümkünse, bu sınıfın denetlenen sürümünü tercih edin [checked_array_iterator](../standard-library/checked-array-iterator-class.md).

> [!NOTE]
> Bu sınıf, C++ standart kitaplığı 'nın bir Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.

## <a name="syntax"></a>Syntax

```cpp
template <class Iterator>
class unchecked_array_iterator;
```

## <a name="remarks"></a>Açıklamalar

Bu sınıf, [stdext](../standard-library/stdext-namespace.md) ad alanında tanımlanır.

Bu, [Checked_array_iterator sınıfının](../standard-library/checked-array-iterator-class.md) denetlenmeyen sürümüdür ve tüm aynı aşırı yüklemeleri ve üyeleri destekler. Denetlenen Yineleyici özelliği kod örnekleriyle ilgili daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<iterator>

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[\<iterator>](../standard-library/iterator.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
