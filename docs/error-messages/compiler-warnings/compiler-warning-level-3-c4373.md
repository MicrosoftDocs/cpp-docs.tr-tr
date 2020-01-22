---
title: Derleyici Uyarısı (düzey 3) C4373
ms.date: 11/04/2016
f1_keywords:
- C4373
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
ms.openlocfilehash: 5891d4679b74695f187fb50bb24fe941882fdcc7
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518354"
---
# <a name="compiler-warning-level-3-c4373"></a>Derleyici Uyarısı (düzey 3) C4373

> '*Function*': sanal işlev '*base_function*' öğesini geçersiz kılıyor; önceki derleyici sürümleri parametreler yalnızca const/volatile niteleyicileri tarafından farklılıyorsa geçersiz kılınmadı

## <a name="remarks"></a>Açıklamalar

Uygulamanız, bir temel sınıftaki sanal bir yöntemi geçersiz kılan türetilmiş bir sınıfta bir yöntem içerir ve geçersiz kılma yöntemindeki parametreler yalnızca sanal yöntemin parametrelerinden bir [const](../../cpp/const-cpp.md) veya [volatile](../../cpp/volatile-cpp.md) niteleyicisi tarafından farklılık gösterir. Bu, derleyicinin bir işlev başvurusunu temel ya da türetilmiş sınıftaki yönteme bağlaması gerektiği anlamına gelir.

Visual Studio 2008 öncesi derleyicinin sürümleri, işlevi temel sınıftaki yönteme bağlayın, sonra bir uyarı iletisi yayınlayın. Derleyicinin sonraki sürümleri `const` veya `volatile` niteleyicisini yoksayar, işlevi türetilmiş sınıftaki yönteme bağlar, sonra Uyarı **C4373**. Bu ikinci davranış, C++ standart ile uyumludur.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği uyarı C4373 oluşturur. Bu sorunu çözmek için, geçersiz kılmayı temel üye işleviyle aynı CV niteleyicilerini kullanabilir ya da bir geçersiz kılma oluşturmayı düşünmüyorsanız, türetilmiş sınıftaki işleve farklı bir ad verebilirsiniz.

```cpp
// c4373.cpp
// compile with: /c /W3
#include <stdio.h>
struct Base
{
    virtual void f(int i) {
        printf("base\n");
    }
};

struct Derived : Base
{
    void f(const int i) {  // C4373
        printf("derived\n");
    }
};

int main()
{
    Derived d;
    Base* p = &d;
    p->f(1);
}
```

```Output
derived
```
