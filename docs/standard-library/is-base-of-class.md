---
title: is_base_of sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_base_of
dev_langs:
- C++
helpviewer_keywords:
- is_base_of class
- is_base_of
ms.assetid: 436f6213-1d4c-4ffc-a588-fc7c4887dd86
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0548de2cd55d1c2988c60020d0a41c12aa3a4bbe
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="isbaseof-class"></a>is_base_of Sınıfı

Tür başka bir temel olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Base, class Derived>
struct is_base_of;
```

### <a name="parameters"></a>Parametreler

`Base` Sınamak için temel sınıf.

`Derived` Sınamak için türetilen tür.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `Base` bir taban sınıf türü `Derived`, aksi takdirde false tutar.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

struct base
    {
    int val;
    };

struct derived
    : public base
    {
    };

int main()
    {
    std::cout << "is_base_of<base, base> == " << std::boolalpha
        << std::is_base_of<base, base>::value << std::endl;
    std::cout << "is_base_of<base, derived> == " << std::boolalpha
        << std::is_base_of<base, derived>::value << std::endl;
    std::cout << "is_base_of<derived, base> == " << std::boolalpha
        << std::is_base_of<derived, base>::value << std::endl;

    return (0);
    }
```

```Output
is_base_of<base, base> == true
is_base_of<base, derived> == true
is_base_of<derived, base> == false
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_convertible Sınıfı](../standard-library/is-convertible-class.md)<br/>
