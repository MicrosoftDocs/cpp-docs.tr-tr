---
title: unchecked_array_iterator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- stdext::unchecked_array_iterator
dev_langs:
- C++
ms.assetid: 693b3b30-4e3a-465b-be06-409700bc50b1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a483d1509ce14a9192c237c5475ec9b8e65d24e6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856195"
---
# <a name="uncheckedarrayiterator-class"></a>unchecked_array_iterator Sınıfı

`unchecked_array_iterator` Sınıfı, bir dizi veya işaretçi denetlenmeyen yineleyici sarmalayın olanak sağlar. Bu sınıf kapsayıcı olarak kullanın (kullanarak [make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator) işlevi) ham işaretçileri veya genel olarak bu uyarılar silencing yerine denetlenmeyen işaretçi Uyarıları yönetmek için hedeflenen bir yöntem olarak diziler için. Mümkünse, bu sınıfın denetlenen sürümünü tercih [checked_array_iterator](../standard-library/checked-array-iterator-class.md).

> [!NOTE]
> Bu sınıf, C++ Standart Kitaplığı, bir Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Iterator>
class unchecked_array_iterator;
```

## <a name="remarks"></a>Açıklamalar

Bu sınıf tanımlanan [stdext](../standard-library/stdext-namespace.md) ad alanı.

Bu denetlenmeyen sürümüdür [checked_array_iterator sınıfı](../standard-library/checked-array-iterator-class.md) ve aşırı ve üyeleri aynı destekler. Kod örnekleri ile denetlenen yineleyici özelliği hakkında daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
