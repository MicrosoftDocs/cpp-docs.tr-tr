---
title: '&lt;işlev&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- functional/std::operator!=
- functional/std::operator==
dev_langs:
- C++
helpviewer_keywords:
- functional operators
ms.assetid: d4b3c760-f3e2-4b65-bdaa-d42e8dd6f5e1
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82ae23b5176ae6986447a9a1218e3bac91c0b741
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltfunctionalgt-operators"></a>&lt;işlev&gt; işleçleri

|||
|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|

## <a name="op_eq_eq"></a>  operator ==

Aranabilir nesne boşsa, testleri.

```cpp
template <class Fty>
bool operator==(const function<Fty>& f, null_ptr_type npc);

template <class Fty>
bool operator==(null_ptr_type npc, const function<Fty>& f);
```

### <a name="parameters"></a>Parametreler

`Fty` Sarmalamak için işlev türü.

`f` İşlev nesnesi

`npc` Bir null işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir başvuru olmayan bir bağımsız değişken işleçlerinin her ikisi de ele bir `function` nesnesi ve bir null işaretçinin sabit olmayan bir bağımsız değişken. Her ikisi de true ise dönmek `function` nesnesidir boş.

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

## <a name="op_neq"></a>  operator! =

Testleri aranabilir nesnesi boş değil.

```cpp
template <class Fty>
bool operator!=(const function<Fty>& f, null_ptr_type npc);

template <class Fty>
bool operator!=(null_ptr_type npc, const function<Fty>& f);
```

### <a name="parameters"></a>Parametreler

`Fty` Sarmalamak için işlev türü.

`f` İşlev nesnesi

`npc` Bir null işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir başvuru olmayan bir bağımsız değişken işleçlerinin her ikisi de ele bir `function` nesnesi ve bir null işaretçinin sabit olmayan bir bağımsız değişken. Her ikisi de true ise dönmek `function` nesnesi boş değil.

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
