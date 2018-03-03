---
title: __FUNC__ | Microsoft Docs
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __func__
dev_langs:
- C++
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5ddb92e84545de175734550eca8911590fa1d539
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="func"></a>__FUNC__

**(C ++ 11)**  Önceden tanımlanmış tanımlayıcı &#95; &#95; func &#95; &#95; örtük olarak kapsayan işlevi nitelenmemiş ve asıl adını içeren bir dize tanımlandı. &#95; &#95; func &#95; &#95; C++ Standart tarafından zorunlu ve bir Microsoft uzantısı değil.

## <a name="syntax"></a>Sözdizimi

```cpp
__func__
```

## <a name="return-value"></a>Dönüş Değeri

İşlev adı içeren döndürür null ile sonlandırılmış const char dizisi karakter.

## <a name="example"></a>Örnek

```cpp
#include <string>
#include <iostream>

namespace Test
{
    struct Foo
    {
        static void DoSomething(int i, std::string s)
        {
           std::cout << __func__ << std::endl; // Output: DoSomething
        }
    };
}

int main()
{
    Test::Foo::DoSomething(42, "Hello");

    return 0;
}
```

## <a name="requirements"></a>Gereksinimler

C ++ 11