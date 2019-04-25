---
title: __FUNC__
ms.date: 10/19/2017
f1_keywords:
- __func__
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
ms.openlocfilehash: eecd3efea6239c92a8bc81c0ed13a9563e5b87d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154301"
---
# <a name="func"></a>__FUNC__

**(C ++ 11)**  Önceden tanımlanmış tanımlayıcının &#95; &#95;func&#95; &#95; açıkça, çevreleyen işlevin nitelenmemiş ve eksiz adını içeren bir dize olarak tanımlanır. &#95;&#95;FUNC&#95; &#95; C++ standardına göre uygulanan ve bir Microsoft uzantısı değil.

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