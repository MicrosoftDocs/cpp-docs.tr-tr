---
title: unchecked_array_iterator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- stdext::unchecked_array_iterator
ms.assetid: 693b3b30-4e3a-465b-be06-409700bc50b1
ms.openlocfilehash: 9b3db474bedca50922334bd4dbd09c71d4e6e987
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399349"
---
# <a name="uncheckedarrayiterator-class"></a>unchecked_array_iterator Sınıfı

`unchecked_array_iterator` Sınıfı bir dizi veya işaretçiyi denetlenmemiş bir yineleyiciye kaydırmanızı sağlar. Bu sınıfı bir sarıcı olarak kullanın (kullanarak [make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator) işlevi) ham işaretçiler veya diziler için bu uyarıları genel olarak susturmak yerine işaretlenmemiş işaretçi uyarılarını yönetmenin hedeflenmiş bir yol olarak için. Mümkünse, bu sınıfının denetlenen sürümünü tercih [checked_array_iterator](../standard-library/checked-array-iterator-class.md).

> [!NOTE]
> Bu sınıf, C++ Standart Kitaplığı'nın bir Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Iterator>
class unchecked_array_iterator;
```

## <a name="remarks"></a>Açıklamalar

Bu sınıf tanımlanan [stdext](../standard-library/stdext-namespace.md) ad alanı.

Bu denetlenmeyen sürümüdür [checked_array_iterator sınıf](../standard-library/checked-array-iterator-class.md) ve aşırı ve üyeleri aynı destekler. Kod örnekleri ile denetlenen yineleyici özelliği hakkında daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
