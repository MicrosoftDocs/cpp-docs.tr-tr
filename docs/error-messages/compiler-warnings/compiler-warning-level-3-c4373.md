---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4373'
title: Derleyici Uyarısı (düzey 3) C4373
ms.date: 11/04/2016
f1_keywords:
- C4373
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
ms.openlocfilehash: a0688f8ed0af1c2854a4449a2fcba31d412a9e4f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160460"
---
# <a name="compiler-warning-level-3-c4373"></a>Derleyici Uyarısı (düzey 3) C4373

> '*Function*': sanal işlev '*base_function*' öğesini geçersiz kılıyor; önceki derleyici sürümleri parametreler yalnızca const/volatile niteleyicileri tarafından farklılıyorsa geçersiz kılınmadı

## <a name="remarks"></a>Açıklamalar

Uygulamanız, bir temel sınıftaki sanal bir yöntemi geçersiz kılan türetilmiş bir sınıfta bir yöntem içerir ve geçersiz kılma yöntemindeki parametreler yalnızca sanal yöntemin parametrelerinden bir [const](../../cpp/const-cpp.md) veya [volatile](../../cpp/volatile-cpp.md) niteleyicisi tarafından farklılık gösterir. Bu, derleyicinin bir işlev başvurusunu temel ya da türetilmiş sınıftaki yönteme bağlaması gerektiği anlamına gelir.

Visual Studio 2008 öncesi derleyicinin sürümleri, işlevi temel sınıftaki yönteme bağlayın, sonra bir uyarı iletisi yayınlayın. Derleyicinin sonraki sürümleri **`const`** veya **`volatile`** niteleyiciyi yoksayar, işlevi türetilmiş sınıftaki yöntemine bağlar, sonra Uyarı **C4373**. Bu ikinci davranış C++ standardına uyar.

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
