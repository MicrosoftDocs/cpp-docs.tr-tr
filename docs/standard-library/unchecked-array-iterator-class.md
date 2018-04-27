---
title: unchecked_array_iterator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- stdext::unchecked_array_iterator
dev_langs:
- C++
ms.assetid: 693b3b30-4e3a-465b-be06-409700bc50b1
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a00c2eb224bc0ff4ab34cfb370ca651f808f1f6
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
