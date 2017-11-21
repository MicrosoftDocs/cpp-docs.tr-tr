---
title: __func__ | Microsoft Docs
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __func__
dev_langs: C++
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 89a3f569a54c035ddb3f4a9ccc17ab5dfe919d0d
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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