---
title: remove_all_extents sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::remove_all_extents
dev_langs:
- C++
helpviewer_keywords:
- remove_all_extents class
- remove_all_extents
ms.assetid: 548dc536-82e7-423a-b8c1-443d66d9632e
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 44207fc9415a03cbfe143c7ab52be77019082e49
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="removeallextents-class"></a>remove_all_extents Sınıfı

Dizi türünden dizi olmayan tür yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct remove_all_extents;

template <class T>
using remove_all_extents_t = typename remove_all_extents<T>::type;
```

### <a name="parameters"></a>Parametreler

`T` Değişiklik türü.

## <a name="remarks"></a>Açıklamalar

Örneği `remove_all_extents<T>` bir değişiklik-dizi türü öğe türüne türü tutan `T` kaldırıldı, tüm dizi boyutları veya `T` varsa `T` bir dizi türü değil.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "remove_all_extents<int> == "
        << typeid(std::remove_all_extents_t<int>).name()
        << std::endl;
    std::cout << "remove_all_extents_t<int[5]> == "
        << typeid(std::remove_all_extents_t<int[5]>).name()
        << std::endl;
    std::cout << "remove_all_extents_t<int[5][10]> == "
        << typeid(std::remove_all_extents_t<int[5][10]>).name()
        << std::endl;

    return (0);
    }
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_extent Sınıfı](../standard-library/remove-extent-class.md)<br/>
