---
description: 'Daha fazla bilgi edinin: &lt; işlevsel &gt; işleçler'
title: '&lt;işlev &gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- functional/std::operator!=
- functional/std::operator==
helpviewer_keywords:
- functional operators
ms.assetid: d4b3c760-f3e2-4b65-bdaa-d42e8dd6f5e1
ms.openlocfilehash: a22e9203e89c041d5ed1925d55d1cd3aa6d61ba3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324245"
---
# <a name="ltfunctionalgt-operators"></a>&lt;işlev &gt; işleçleri

## <a name="operator"></a><a name="op_eq_eq"></a> işleç = =

Çağrılabilir nesne boş ise sınar.

```cpp
template <class Fty>
    bool operator==(const function<Fty>& f, null_ptr_type npc);

template <class Fty>
    bool operator==(null_ptr_type npc, const function<Fty>& f);
```

### <a name="parameters"></a>Parametreler

*Fty*\
Sarılacağı işlev türü.

*vadeli*\
İşlev nesnesi

*NPC*\
Null işaretçi.

### <a name="remarks"></a>Açıklamalar

İşleçler her ikisi de bir nesne başvurusu olan bir bağımsız değişken `function` ve null işaretçi sabiti olan bir bağımsız değişken alır. Her ikisi de yalnızca nesne boşsa true değeri döndürür `function` .

### <a name="example"></a>Örnek

```cpp
// std__functional__operator_eq.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
{
    return (-val);
}

int main()
{
    std::function<int(int)> fn0;
    std::cout << std::boolalpha << "empty == "
        << (fn0 == 0) << std::endl;

    std::function<int(int)> fn1(neg);
    std::cout << std::boolalpha << "empty == "
        << (fn1 == 0) << std::endl;

    return (0);
}
```

```Output
empty == true
empty == false
```

## <a name="operator"></a><a name="op_neq"></a> işleç! =

Çağrılabilir nesne boş değilse sınar.

```cpp
template <class Fty>
    bool operator!=(const function<Fty>& f, null_ptr_type npc);

template <class Fty>
    bool operator!=(null_ptr_type npc, const function<Fty>& f);
```

### <a name="parameters"></a>Parametreler

*Fty*\
Sarılacağı işlev türü.

*vadeli*\
İşlev nesnesi

*NPC*\
Null işaretçi.

### <a name="remarks"></a>Açıklamalar

İşleçler her ikisi de bir nesne başvurusu olan bir bağımsız değişken `function` ve null işaretçi sabiti olan bir bağımsız değişken alır. Her ikisi de yalnızca nesne boş değilse true değerini döndürür `function` .

### <a name="example"></a>Örnek

```cpp
// std__functional__operator_ne.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0;
    std::cout << std::boolalpha << "not empty == "
        << (fn0 != 0) << std::endl;

    std::function<int (int)> fn1(neg);
    std::cout << std::boolalpha << "not empty == "
        << (fn1 != 0) << std::endl;

    return (0);
    }
```

```Output
not empty == false
not empty == true
```
