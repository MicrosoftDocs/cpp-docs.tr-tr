---
title: __FUNC__ | Microsoft Docs
ms.custom: ''
ms.date: 10/19/2017
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __func__
dev_langs:
- C++
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d78a249fe5b111c17c29895edcdc3fa5ba2f27a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413602"
---
# <a name="func"></a>__FUNC__

**(C ++ 11)**  Önceden tanımlanmış tanımlayıcı &#95; &#95;func&#95; &#95; kapsayan işlevi nitelenmemiş ve asıl adını içeren bir dize örtük olarak tanımlanır. &#95;&#95;FUNC&#95; &#95; C++ Standart tarafından zorunlu ve bir Microsoft uzantısı değil.

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

C++11