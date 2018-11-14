---
title: '&lt;işlevsel&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- functional/std::operator!=
- functional/std::operator==
helpviewer_keywords:
- functional operators
ms.assetid: d4b3c760-f3e2-4b65-bdaa-d42e8dd6f5e1
ms.openlocfilehash: 6fd4e25b3ca7b56e2221cb99b64f7c8e109bf452
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521927"
---
# <a name="ltfunctionalgt-operators"></a>&lt;işlevsel&gt; işleçleri

|||
|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|

## <a name="op_eq_eq"></a>  işleç ==

Çağrılabilir nesnesi boş olup olmadığını sınar.

```cpp
template <class Fty>
bool operator==(const function<Fty>& f, null_ptr_type npc);

template <class Fty>
bool operator==(null_ptr_type npc, const function<Fty>& f);
```

### <a name="parameters"></a>Parametreler

*Fty*<br/>
Kaydırmak için işlev türü.

*f*<br/>
İşlev nesnesi

*npc*<br/>
Null bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Her iki işleçleri başvuru bir bağımsız değişken alır bir `function` nesnesi ve bir null işaretçi sabit bir bağımsız değişken. Her ikisi de yalnızca, true döndürür `function` nesnesi boş.

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

## <a name="op_neq"></a>  işleç! =

Çağrılabilir nesnesi boş olup olmadığını sınar.

```cpp
template <class Fty>
bool operator!=(const function<Fty>& f, null_ptr_type npc);

template <class Fty>
bool operator!=(null_ptr_type npc, const function<Fty>& f);
```

### <a name="parameters"></a>Parametreler

*Fty*<br/>
Kaydırmak için işlev türü.

*f*<br/>
İşlev nesnesi

*npc*<br/>
Null bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Her iki işleçleri başvuru bir bağımsız değişken alır bir `function` nesnesi ve bir null işaretçi sabit bir bağımsız değişken. Her ikisi de yalnızca, true döndürür `function` nesnesi boş değil.

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

## <a name="see-also"></a>Ayrıca bkz.

[\<işlev >](../standard-library/functional.md)<br/>
