---
title: is_same sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_same
dev_langs:
- C++
helpviewer_keywords:
- is_same class
- is_same
ms.assetid: d9df6c1d-c270-4ec2-802a-af275648dd1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07b886b805eb551831ad2d559b041df0d38c5987
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="issame-class"></a>is_same Sınıfı

İki tür aynıysa testleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty1, class Ty2>
struct is_same;
```

### <a name="parameters"></a>Parametreler

`Ty1` Sorgu için ilk türü.

`Ty2` Sorgu için ikinci türü.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türleri `Ty1` ve `Ty2` aynı türdeyse, aksi takdirde false tutar.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_same.cpp
// compile with: /EHsc
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
    std::cout << "is_same<base, base> == " << std::boolalpha
        << std::is_same<base, base>::value << std::endl;
    std::cout << "is_same<base, derived> == " << std::boolalpha
        << std::is_same<base, derived>::value << std::endl;
    std::cout << "is_same<derived, base> == " << std::boolalpha
        << std::is_same<derived, base>::value << std::endl;
    std::cout << "is_same<int, int> == " << std::boolalpha
        << std::is_same<int, int>::value << std::endl;
    std::cout << "is_same<int, const int> == " << std::boolalpha
        << std::is_same<int, const int>::value << std::endl;

    return (0);
    }

```

```Output
is_same<base, base> == true
is_same<base, derived> == false
is_same<derived, base> == false
is_same<int, int> == true
is_same<int, const int> == false
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_convertible Sınıfı](../standard-library/is-convertible-class.md)<br/>
[is_base_of Sınıfı](../standard-library/is-base-of-class.md)<br/>
