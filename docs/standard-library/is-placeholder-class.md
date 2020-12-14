---
description: 'Hakkında daha fazla bilgi edinin: is_placeholder sınıfı'
title: is_placeholder Sınıfı
ms.date: 11/04/2016
f1_keywords:
- functional/std::is_placeholder
helpviewer_keywords:
- is_placeholder class
ms.assetid: 2b21a792-96d1-4bb8-b911-0db796510835
ms.openlocfilehash: 84d73da6ffe2446a8448b0ff5f30604d259493b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230666"
---
# <a name="is_placeholder-class"></a>is_placeholder Sınıfı

Tür bir yer tutucu ise sınar.

## <a name="syntax"></a>Syntax

struct is_placeholder {static const int Value;};

## <a name="remarks"></a>Açıklamalar

`value`Tür `Ty` bir yer tutucu değilse, sabit değer 0 ' dır; Aksi takdirde, değeri, bağlandığı işlev çağrısı bağımsız değişkeninin konumudur. `N`N. yer tutucunun değerini öğrenmek için bunu kullanırsınız `_N` .

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
