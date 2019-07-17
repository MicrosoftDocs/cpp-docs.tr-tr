---
title: is_placeholder Sınıfı
ms.date: 11/04/2016
f1_keywords:
- functional/std::is_placeholder
helpviewer_keywords:
- is_placeholder class
ms.assetid: 2b21a792-96d1-4bb8-b911-0db796510835
ms.openlocfilehash: 9fa7d4aaade6244fe26f89f3a667598d39471a47
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245144"
---
# <a name="isplaceholder-class"></a>is_placeholder Sınıfı

Bir yer tutucu türü olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

Yapı is_placeholder {statik const Int değeri;};

## <a name="remarks"></a>Açıklamalar

Sabit değer `value` 0 ise türü `Ty` değil yer tutucu; Aksi takdirde, değeri için bağlayan işlev çağrısı bağımsız değişkeni konumudur. Değeri belirlemek için kullandığınız `N` n. yer tutucunun `_N`.

## <a name="example"></a>Örnek

```cpp
// std__functional__is_placeholder.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

using namespace std::placeholders;

template<class Expr>
void test_for_placeholder(const Expr&)
{
    std::cout << std::is_placeholder<Expr>::value << std::endl;
}

int main()
{
    test_for_placeholder(3.0);
    test_for_placeholder(_3);

    return (0);
}
```

```Output
0
3
```
