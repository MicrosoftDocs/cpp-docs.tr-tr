---
title: '&lt;işlevsel&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- functional/std::operator!=
- functional/std::operator==
helpviewer_keywords:
- functional operators
ms.assetid: d4b3c760-f3e2-4b65-bdaa-d42e8dd6f5e1
ms.openlocfilehash: b396e5c692129821c0deb9aef9469a5c54e600b0
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78876354"
---
# <a name="ltfunctionalgt-operators"></a>&lt;işlevsel&gt; işleçleri

## <a name="op_eq_eq"></a>işleç = =

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

*f*\
İşlev nesnesi

*NPC*\
Null işaretçi.

### <a name="remarks"></a>Açıklamalar

İşleçler her ikisi de `function` nesnesine başvuru olan bir bağımsız değişken ve null işaretçi sabiti olan bir bağımsız değişken alır. Her ikisi de yalnızca `function` nesnesi boşsa true değeri döndürür.

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

## <a name="op_neq"></a>işleç! =

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

*f*\
İşlev nesnesi

*NPC*\
Null işaretçi.

### <a name="remarks"></a>Açıklamalar

İşleçler her ikisi de `function` nesnesine başvuru olan bir bağımsız değişken ve null işaretçi sabiti olan bir bağımsız değişken alır. Her ikisi de yalnızca `function` nesnesi boş değilse true değerini döndürür.

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
